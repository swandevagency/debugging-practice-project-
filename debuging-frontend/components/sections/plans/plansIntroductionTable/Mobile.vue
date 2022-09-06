<template>
    <div>
        <div class="plans-introduction-table-section-wrapper">
            <div class="plans-introduction-table-section">
                
                <div class="introduction-table">
                    <div class="introduction-table-header">
                        <h6>Elit elit incididunt laborum elit et.</h6>
                    </div>
                    <div class="introduction-table-options">
                        <div>
                            <p>Basic</p>
                            <TrueIcon class="true" />
                        </div>
                        <div>
                            <p>Advanced</p>
                            <FalseIcon class="false" />
                        </div>
                        <div>
                            <p>Professional</p>
                            <TrueIcon class="true" />
                        </div>
                    </div>
                </div>

                <div class="introduction-table">
                    <div class="introduction-table-header">
                        <h6>Elit elit incididunt laborum elit et.</h6>
                    </div>
                    <div class="introduction-table-options">
                        <div>
                            <p>Basic</p>
                            <TrueIcon class="true" />
                        </div>
                        <div>
                            <p>Advanced</p>
                            <FalseIcon class="false" />
                        </div>
                        <div>
                            <p>Professional</p>
                            <TrueIcon class="true" />
                        </div>
                    </div>
                </div>

                <div class="introduction-table">
                    <div class="introduction-table-header">
                        <h6>Elit elit incididunt laborum elit et.</h6>
                    </div>
                    <div class="introduction-table-options">
                        <div>
                            <p>Basic</p>
                            <TrueIcon class="true" />
                        </div>
                        <div>
                            <p>Advanced</p>
                            <FalseIcon class="false" />
                        </div>
                        <div>
                            <p>Professional</p>
                            <TrueIcon class="true" />
                        </div>
                    </div>
                </div>


                <div class="introduction-table">
                    <div class="introduction-table-header">
                        <h6>Elit elit incididunt laborum elit et.</h6>
                    </div>
                    <div class="introduction-table-options">
                        <div>
                            <p>Basic</p>
                            <TrueIcon class="true" />
                        </div>
                        <div>
                            <p>Advanced</p>
                            <FalseIcon class="false" />
                        </div>
                        <div>
                            <p>Professional</p>
                            <TrueIcon class="true" />
                        </div>
                    </div>
                </div>


                <div class="introduction-table">
                    <div class="introduction-table-header">
                        <h6>Elit elit incididunt laborum elit et.</h6>
                    </div>
                    <div class="introduction-table-options">
                        <div>
                            <p>Basic</p>
                            <TrueIcon class="true" />
                        </div>
                        <div>
                            <p>Advanced</p>
                            <FalseIcon class="false" />
                        </div>
                        <div>
                            <p>Professional</p>
                            <TrueIcon class="true" />
                        </div>
                    </div>
                </div>


                <div class="introduction-table">
                    <div class="introduction-table-header">
                        <h6>Elit elit incididunt laborum elit et.</h6>
                    </div>
                    <div class="introduction-table-options">
                        <div>
                            <p>Basic</p>
                            <TrueIcon class="true" />
                        </div>
                        <div>
                            <p>Advanced</p>
                            <FalseIcon class="false" />
                        </div>
                        <div>
                            <p>Professional</p>
                            <TrueIcon class="true" />
                        </div>
                    </div>
                </div>


                <div class="introduction-table">
                    <div class="introduction-table-header">
                        <h6>Elit elit incididunt laborum elit et.</h6>
                    </div>
                    <div class="introduction-table-options">
                        <div>
                            <p>Basic</p>
                            <TrueIcon class="true" />
                        </div>
                        <div>
                            <p>Advanced</p>
                            <FalseIcon class="false" />
                        </div>
                        <div>
                            <p>Professional</p>
                            <TrueIcon class="true" />
                        </div>
                    </div>
                </div>


                <div class="introduction-table">
                    <div class="introduction-table-header">
                        <h6>Elit elit incididunt laborum elit et.</h6>
                    </div>
                    <div class="introduction-table-options">
                        <div>
                            <p>Basic</p>
                            <TrueIcon class="true" />
                        </div>
                        <div>
                            <p>Advanced</p>
                            <FalseIcon class="false" />
                        </div>
                        <div>
                            <p>Professional</p>
                            <TrueIcon class="true" />
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
    components:{
        TrueIcon: () => import ('@/components/icons/tableIcons/trueIcon.vue'),
        FalseIcon: () => import ('@/components/icons/tableIcons/falseIcon.vue'),
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.plans-introduction-table-section-wrapper{
    @include mq(lg) {
        display: none;
    }
}

.plans-introduction-table-section{
    width: 100%;
    border-radius: 10px;
    margin-top: 80px;    
    margin-bottom: 100px;
    border: 1px solid $primary;
}

.introduction-table{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;    
}

.introduction-table-header{
    width: 100%;
    padding: 16px;
    text-align: center;
}

.introduction-table-options{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    

    &>div{
        width: 100%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
        border-top: 1px solid $primary;
        
        &:last-child{
            border-bottom: 1px solid $primary;
        }

        p{
            flex-basis: 50%;
            text-align: center;
            border-right: 1px solid $primary;
        }

        .true, 
        .false{
            flex-basis: 50%;
            width: 16px;
            height: 16px;
            border-radius: 50%;
        }

        .false{
            flex-basis: 50%;
        }
         
    }
}


</style>