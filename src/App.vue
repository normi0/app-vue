<script>
export default{
  name: 'App',
  data(){
    return{
      title:'My First App ;)'
    }
  }
}
</script>

<template>
<h1>{{ title }}</h1>
</template>

<style scoped>
#app{
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  color: rgb(2, 2, 70);
  margin-top: 60px;
}
h1{
display: flex;
justify-content: center;
align-content: center;
border-bottom: 1px solid lightpink;
padding-bottom:10px ;
}
</style>
