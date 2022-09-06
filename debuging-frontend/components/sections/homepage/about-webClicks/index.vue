<template>
  <div class="about-webclicks-section-container">
    <div class="about-webclicks-intro-wrapper">
      <div class="about-webclicks-info-wrapper">
        <h5>about webclicks</h5>
        <h2>Our team is made of experts</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Viverra
          ipsum nunc aliquet bibendum enim facilisis gravida neque. Egestas
          fringilla phasellus faucibus scelerisque. Arcu cursus vitae congue
          mauris rhoncus aenean vel. Urna et pharetra pharetra massa. Etiam sit
          amet nisl purus in mollis nunc. Eu volutpat odio facilisis mauris sit.
        </p>
      </div>
      <div class="about-webclicks-svg-wrapper">
        <img
          src="/image/home-page/about-webclicks.png"
          alt="about webclicks picture"
        />
      </div>
    </div>
    <div class="about-webclicks-our-team-wrapper">
      <div class="about-webclicks-our-team-title">
        <h5>our team</h5>
        <h2>Our team is made of experts</h2>
      </div>
      <div class="about-webclicks-our-team-container">
        <TeamMember
          class="team-member-component-item"
          v-for="teamMember in teamMembers"
          :key="teamMember.id"
          :pictureUrl="teamMember.image"
          :name="teamMember.name"
          :role="teamMember.role"
        />
      </div>
    </div>
    <div class="about-webclicks-button-container">
      <ButtonItem buttonText="Get to know us" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      teamMembers: [
        {
          id: '12313123',
          image: '/imgs/testProfile.jpg',
          name: 'shayan azali',
          role: 'Frontend developer',
        },
        {
          id: '12546546313123',
          image: '/imgs/testProfile.jpg',
          name: 'shayan azali',
          role: 'Frontend developer',
        },
        {
          id: '12313127683',
          image: '/imgs/testProfile.jpg',
          name: 'shayan azali',
          role: 'Frontend developer',
        },
        {
          id: '12314563123',
          image: '/imgs/testProfile.jpg',
          name: 'shayan azali',
          role: 'Frontend developer',
        },
      ],
    }
  },
  components: {
    TeamMember: () => import('@/components/modules/team-member.vue'),
    AboutUsSection: () => import('@/components/icons/about-us-section-svg.vue'),
    ButtonItem: () => import('@/components/modules/button-item.vue'),
  },
})
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';
.about-webclicks-section-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.about-webclicks-intro-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.about-webclicks-svg-wrapper {
  width: 68%;
}
.about-webclicks-info-wrapper {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  margin-bottom: 50px;
  h5 {
    color: $subTitle-color;
    font-size: 14px;
    text-transform: uppercase;
    font-weight: 500;
    //todo need to fix the font family
    // font-family: 'Space Grotesk';
  }
  h2 {
    line-height: 42px;
    margin-bottom: 30px;
    margin-top: 8px;
    @include mq(lg) {
      line-height: 51px;
    }
  }
  p {
    line-height: 33px;
    font-size: 18px;
  }
}
.about-webclicks-our-team-wrapper {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  margin-top: 50px;
  width: 100%;
}
.about-webclicks-our-team-title {
  width: 100%;
  h5 {
    color: $subTitle-color;
    font-size: 14px;
    text-transform: uppercase;
    font-weight: 500;
    //todo need to fix the font family
  }
  h2 {
    margin-top: 8px;
    margin-bottom: 30px;
    @include mq(lg) {
      margin-bottom: 0px;
    }
  }
}
.about-webclicks-our-team-container {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  .team-member-component-item {
    flex-basis: calc(100% / 2 - 30px);
    margin-bottom: 30px;
  }
}
.about-webclicks-button-container {
  margin-top: 50px;
}
@include mq(lg) {
  .about-webclicks-intro-wrapper {
    flex-direction: row-reverse;
    justify-content: space-between;
  }
  .about-webclicks-info-wrapper {
    flex-basis: 50%;
  }
  .about-webclicks-svg-wrapper {
    flex-basis: 40%;
    width: unset;
  }
  .about-webclicks-our-team-container {
    margin-top: 85px;
    .team-member-component-item {
      flex-basis: calc(100% / 4 - 30px);
      margin-bottom: 0px;
    }
  }
  .about-webclicks-button-container {
    margin-top: 80px;
  }
}
</style>
