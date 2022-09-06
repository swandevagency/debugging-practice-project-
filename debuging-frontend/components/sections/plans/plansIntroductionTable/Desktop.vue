<template>
    <div>
        <div class="plans-introduction-table-section-wrapper">
            <div>
                <table class="plans-introduction-table-section">  
                    <thead class="introduction-table-header">
                        <th></th>
                        <th>Basic</th>
                        <th>Advanced</th>
                        <th>Professional</th>
                    </thead>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Number of admins</td>
                        <td class="introduction-table-boolean">1 Admin</td>
                        <td class="introduction-table-boolean">3 Admins</td>
                        <td class="introduction-table-boolean">Unlimited admins</td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
    
                    <tr class="introduction-table-options">
                        <td class="introduction-table-title">Elit elit incididunt laborum elit et.</td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                        <td class="introduction-table-boolean"><FalseIcon /></td>
                        <td class="introduction-table-boolean"><TrueIcon /></td>
                    </tr>
                </table>
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
    display: none;
    &>div{
        border-radius: 10px;
        margin-top: 80px;    
        margin-bottom: 100px;
    }
    @include mq(lg) {
        display: initial;
    }
}

.plans-introduction-table-section{
    width: 100%;
    box-shadow: 0px 0px 0px 1px $primary;
    border-radius: 10px;
    text-align: center;
    border-collapse: collapse;   
    
    thead{
        border-bottom: 1px solid $primary;
    }
    // todo: (Space Grotesk) font problem 
    th{
        border-left: 1px solid $primary;
        padding: 15px; 
        font-family: 'Space Grotesk';
        font-style: normal;
        font-weight: 700;
        font-size: 24px;
        color: $title-color;

        &:first-child{
            border-left: none;
        }
    }

    tr{
        border-bottom: 1px solid $primary;
        &:last-child{
            border-bottom: none;
        }
    }

    td{
        border-left: 1px solid $primary;
        padding: 15px;
        color: $title-color;
        font-weight: 300;
        
        &:first-child{
            font-weight: 500;
            border-left: none;
        }
    }

}



</style>