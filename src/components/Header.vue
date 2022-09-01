<template>
  <header>
    <h1>Income Tracker</h1>
    <div class="total-incoome">${{totalincome}}</div>
  </header>
</template>

<script>
export default {
  props:['totalincome']
}
</script>

<style scoped>
header{
  display: flex;
 border-bottom: 5px solid #ffce00;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
  background: #313131;
}
header h1{
  color: #eee;
  font-size: 28px;
}
header .total-incoome{
  font-family: 'fira Code' ,'Fira Sans',sans-serif;
  background-color: #ffce00;
  color: #fff;
  font-size: 20px;
  padding: 5px 10px;
  font-weight: 900px;
  min-width: 100px;
  text-align: center;
  border-radius: 8px;
  box-shadow: inset 0px 0px 6px rgba(0,0,0,0.25);
  text-shadow: 0px 3px 3px rgba(0,0,0,0.25 );
}
form input:first-of-type{

  border-radius: 8px 0px 0px 8px;
}
form input:last-of-type{
  border-radius: 0px 8px 8px 0px;
}
</style>