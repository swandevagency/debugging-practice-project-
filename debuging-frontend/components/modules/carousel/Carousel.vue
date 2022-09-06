<template>
  <div :class="['carousel', wrapperClasses ? wrapperClasses : '']" ref="carousel">
    <div class="slider-wrapper">
      <div class="inner" ref="inner">
        <slot></slot>
      </div>
    </div>
    <div class="carousel-nav" v-if="this.optionsObject.arrows">
      <button class="prev" @click="movePrev()">prev</button>
      <button class="next" @click="moveNext()">next</button>
    </div>
    <div class="carousel-dots-wrapper" ref="dotsWrapper" v-if="this.optionsObject.dots">
      <button v-for='index in this.numberOfDots' :key='index' :class="[ 'carousel-dot', `step-${index}` ]" :step="index" @click='goToStep(index)'></button>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Carousel",
    props: {
      wrapperClasses: String,
      optionsArray: Array,
    },
    
    data() {
      return {
        carouselCreated: false,
        windowWidth: 0,
        optionsObject: {},
        innerWidth: 0,
        slideWidth: 0,
        stepSize: 0,
        currentStep: 0,
        innerPosition: 0,
        numberOfDots: 0,
      }
    },

    methods: {
      calculateInnerPosition( decrease ) {
        if ( decrease ) {
          if ( this.optionsObject.loop && this.innerPosition <= 0 ) {
            this.innerPosition = this.innerWidth - ( this.stepSize );  
          } else if ( this.innerPosition > 0 ){
            this.innerPosition -= this.stepSize;
          }
        } else {
          if ( this.optionsObject.loop && this.innerPosition >= ( this.innerWidth - ( this.stepSize ) ) ) {
            this.innerPosition = 0;  
          } else if ( this.innerPosition < ( this.innerWidth - ( this.stepSize ) ) ) {
            this.innerPosition += this.stepSize;
          }
        }
      },

      findOptionsFromArray ( windowWidth , optionsArray ) {
        let chosenOption;
        let validBreakpointsArray = []
        let choseonBreakpoint;
        for( let i = 0; i < optionsArray.length; i++ ){
          validBreakpointsArray.push( optionsArray[i].breakpoint )
        }
        if ( windowWidth >= 1440 ) {
          choseonBreakpoint = validBreakpointsArray.includes( -1 ) ? -1 : Math.max( ...validBreakpointsArray );
        }
        else {
          if ( validBreakpointsArray.some(breakpoint => breakpoint > windowWidth ) ) {
            choseonBreakpoint = Math.min( ...validBreakpointsArray.filter( breakpoint => breakpoint > windowWidth ) )
          } else {
            choseonBreakpoint = Math.max( ...validBreakpointsArray )
          }
        }
        chosenOption = optionsArray.filter( options => options.breakpoint === choseonBreakpoint );
        return chosenOption[0];
      },

      moveNext() {
        this.calculateInnerPosition( false );
        this.$refs.inner.style.cssText = `transform: translateX(${ this.innerPosition }px)`;
        this.findandActivateCurrentStep()
      },

      movePrev() {
        this.calculateInnerPosition( true );
        this.$refs.inner.style.cssText = `transform: translateX(${ this.innerPosition }px)`;
        this.findandActivateCurrentStep()
      },

      goToStep( step ) {
        this.innerPosition = this.stepSize * ( step - 1 );
        this.$refs.inner.style.cssText = `transform: translateX(${ this.innerPosition }px)`;
        this.findandActivateCurrentStep()  
      },

      findandActivateCurrentStep() {
        if (this.optionsObject.dots) {
          this.currentStep = this.innerPosition / this.stepSize + 1;
          const dotButtons = document.querySelectorAll( `.carousel.${ this.wrapperClasses } .carousel-dot` );
          dotButtons.forEach(dot => dot.classList.remove( "active" ))
          document.querySelector( `.carousel.${ this.wrapperClasses } .carousel-dot[step="${ this.currentStep }"]` ).classList.add( "active" );
        }
      }
    },

    mounted() {
      // get windows width
      this.windowWidth = window.innerWidth;

      // find carousel Options for window size 
      this.optionsObject = this.findOptionsFromArray( this.windowWidth, this.optionsArray )

      // variables
      const carouselSelector = this.$refs.carousel;
      const carouselStyles = window.getComputedStyle( carouselSelector );
      const innerSelector = this.$refs.inner;
      const dotsWrapper = this.$refs.dotsWrapper
      const slidesSelector = document.querySelectorAll( `.carousel.${ this.wrapperClasses } .slides` );
      const carouselWidth = carouselSelector.clientWidth - parseFloat( carouselStyles.paddingLeft ) - parseFloat( carouselStyles.paddingRight );
      this.numberOfDots = slidesSelector.length / this.optionsObject.itemsPerStep;

      // calculated variables
      this.slideWidth = ( carouselWidth / this.optionsObject.itemsPerSlide );
      const itemsWidth = this.slideWidth - ( this.optionsObject.itemsMargin * 2 );
      this.stepSize = this.slideWidth * this.optionsObject.itemsPerStep;

      // add width and margin for slides
      for (let i = 0; i < slidesSelector.length; i++) {
        slidesSelector[i].style.cssText = `margin-left:${ this.optionsObject.itemsMargin }px;margin-right:${ this.optionsObject.itemsMargin }px;width:${ itemsWidth }px !important;`;
      }

      
      // set variables after adding slides width and margins
      this.innerWidth = innerSelector.offsetWidth;

      console.log( 'carouselWidth', carouselWidth )
      console.log( 'numberOfDots' );
      console.log( this.numberOfDots );
      console.log( "inner position =" + this.innerWidth );
      console.log( itemsWidth );
      console.log( this.windowWidth );

      // lazyload
      this.carouselCreated = true;
    },
  }
</script>

<style lang="scss" scoped>
  @import '@/assets/scss/helpers/variables';

  .carousel {
    position: relative;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding-bottom: 3rem;

    &.testimonials-carousel {
      padding: 0 4rem 2rem 4rem;

      @include mq-max(xl) {
        padding: 0 3rem 2rem 3rem;
      }
      @include mq-max(lg) {
        padding: 0 2rem 2rem 2rem;
      }
      @include mq-max(sm) {
        padding: 0 0 2rem 0;
      }
    }
  }
  .slider-wrapper {
    width: 100%;
    overflow: hidden;
  }

  .inner {
    display: inline-flex;
    align-items: baseline;
    transition: 0.2s all linear;
  }

  .carousel-nav {
    position: absolute;
    display: flex;
    justify-content: space-between;
    width: 105%;

    .testimonials-carousel & {
      width: 100%;
      top: 45%;
    }

    button {
      background-color: unset;
      background-size: contain;
      background-repeat: no-repeat;
      width: 40px;
      height: 40px;
      border: none;
      font-size: 0;
      cursor: pointer;

      &.next {
        @include icon("chevron-right");
      }
      &.prev {
        @include icon("chevron-left");
      }
    }
  }
  .carousel-dots-wrapper {
    width: 100%;
    position: absolute;
    bottom: 0;
    z-index: 10;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .carousel-dot {
    padding: 0;
    width: 7px;
    height: 7px;
    border-radius: 15px;
    background-color: $gray-300;
    border: none;
    margin: 3px;
    cursor: pointer;
    transition: 0.2s all linear;

    &.active {
      background-color: $secondary;
      width: 20px;
    }
  }
</style>