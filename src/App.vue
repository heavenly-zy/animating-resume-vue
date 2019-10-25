<template>
  <div id="app">
    <pre>{{code}}</pre>
    <div v-html='styleCode'></div>
  </div>
</template>

<script>

  export default {
    name: 'app',
    components: {

    },
    data(){
      return{
        code:``,
        finallyCode:`
html{
   background:red;
}`
      }
    },
    created(){
      var n = 0
      setInterval(()=>{
        this.code = this.finallyCode.slice(0,n)
        n += 1
      },100)
    },
    computed:{
      styleCode(){
        return '<style>' + this.code + '</style>'
        }
        }
        }
</script>

<style>

</style>
