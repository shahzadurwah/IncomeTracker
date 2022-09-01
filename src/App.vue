<template>
<Header :totalincome="state.totalincome"></Header>
  <Form  @add-income="addincome"></Form>
  <incomeList :state="state"></incomeList>
</template>

<script>
import Header from './components/Header.vue'
import Form from './components/Form.vue'
import incomeList from './components/incomeList.vue'
import { reactive,computed } from 'vue'
export default {
    setup(){
      const state=reactive({
        income:[],
        totalincome:computed(()=>{
          let temp=0;
          if(state.income.length>0){
            for(let i=0;i<state.income.length;i++){
              temp +=state.income[i].value;
            }
          }
          return temp;
        })
      });
      function addincome(data){
        // let d=data.date.split("-");
        // let newD=new Date(d[0],d[1],d[2]);
        state.income=[...state.income,{
          id:Date.now(),
          desc:data.desc,
          value:data.value,
          date:data.date
        }];
        console.log(state.income);
      }
      return{
        state,
        addincome
      }
    },

    components:{
      Header,
      Form,
      incomeList
    }
  }
  

</script>

<style>
*{
  padding: 0px;
  margin: 0px;
  box-sizing: border-box;
  font-family: sans-serif;
}
body{
  background: #eee;
}
</style>