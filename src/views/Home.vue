<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import jsonp from 'jsonp'
export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data() {
    return {
      data: '',
    }
  },
  mounted() {
    let url = 'activity/servicetime'
    // axios.get(url).then(()=>{

    // })
    jsonp(url, (err, res)=>{
      let result = res;
      this.data = result;
    })
  }
}
</script>
