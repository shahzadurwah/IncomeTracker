<template>
    <form @submit.prevent="formHandler">
        <input type="text" placeholder="Description...." v-model="formData.desc">
        <input type="number" placeholder="value...." v-model="formData.value"/>
        <input type="date" placeholder="Date...." v-model="formData.date"/>
        <input type="submit" value="SUBMIT"/>
    </form>
</template>
<script>
import { reactive } from "vue"
export default {
    props:{
        state:Object
    },
    setup(props,{emit}){
        const formData=reactive({
            desc:null,
            value:null,
            date:null
        });
        function formHandler(){
            emit('add-income',{
                desc:formData.desc,
                value:formData.value,
                date:formData.date
            });
            formData.desc=null;
            formData.value=null;
            formData.date=null;
        }
        return{
            formData,
            formHandler
        }
    }
}
</script>
<style scoped>
form{
    display: flex;
    margin-top: 30px;
    justify-content: center;
}
form input{
    border: none;
    outline: none;
    color: #888;
    font-size: 20px;

}
form input::placeholder{
    color: #aaa;
}

form input:not([type="submit"]){
    display: block;
    background: #fff;
    border: none;
    outline: none;
    padding: 5px 15px;
}
form input[type="submit"]{
    display: block;
    background-color: #ffce00;
    color: #fff;
    font-weight: 500px;
    text-shadow: 0px 1px 3px rgba(0,0,0,0.2);
    border: none;
    outline: none;
    padding: 5px 15px;
    cursor: pointer;
}
</style>