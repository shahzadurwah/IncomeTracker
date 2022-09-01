<template>
    <div class="income-list">
        
        <incomeitem v-for="data in state.income" :key="data" :income="data"></incomeitem>
    </div>
</template>

<script>
import incomeitem from './incomeitem.vue'
export default {
    name:'incomeList',
    props:{
        state:Object
    },
    components:{
        incomeitem
    }
}
</script>

<style scoped>
 .income-list{
     padding: 15px;
     margin-top: 30px;
 }
</style>