<script>
  import FormularioVue from './components/FormularioVue.vue';
  export default{
    name: 'App',
    components: { FormularioVue }
  }
  
</script>

<template>
  <FormularioVue />
</template>


<style>
#app{
    font-family: Arial, Helvetica, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #280000;
    margin-top: 60px;
}
body{
    margin: 0;
    background: #eee;
}
</style>