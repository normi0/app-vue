<template>
  <section>
    <h1>{{ title }}</h1>
    <input type="text" ref="name">
    <button @click="handleClick">click Me</button>
  </section>
 
  </template>


<script>
export default{
  name: 'App',
  data(){
    return{
      title:'My First App ;)'
    }
  },
  methods :{
     handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
     }
  }
}
</script>



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
