<template>
  <div>
    <h2>我爱你赵丽颖</h2>
    
    <Child></Child>
  </div>
</template>
<script>
import Child from './Child.vue'
export default {
  name: 'ScopedTest',
  components:{
    Child
  },
  data() {
    return {
      
    };
  },
}
</script>

<style scoped>
div >>> h2{
  color: red;
}
</style>
