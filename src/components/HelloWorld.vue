<template>
  <main>
    <h1>API DETAILS</h1>
    <table>
      <tr>
        <td>name</td>
        <td>salary</td>
        <td>age</td>
      </tr>
    </table>
  </main>
</template>

<script>
  import Vue from "vue";
  // import axios from "axios"
  // import Vueaxios from "vue-axios"
  import VueAxios from 'vue-axios'
  Vue.use(VueAxios.axios)
  export default {
    name: "HelloWorld",
    data(){
      return{list:undefined}
    },
    mounted() {
      Vue.axios.get('http://dummy.restapiexample.com/api/v1/employees')
        .then((resp) => {
          this.list=resp.data.data;
          console.warn(resp.data.data)
        })

    }
  }
</script>

<style>

</style>