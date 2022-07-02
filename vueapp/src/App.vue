<template>
<div id="app">
  <DollarConverter>Loading...</DollarConverter>
</div>
</template>



<script>
import DollarConverter from "@/components/dollar-converter";

export default {
  name:"app",
  components:{
    DollarConverter
  },
  };

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
