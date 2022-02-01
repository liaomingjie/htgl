<template>
  <div>
    <el-button type="primary" v-if="$hasBp('btn.Test111.add')">添加</el-button>
    <el-button type="warning" v-if="$hasBp('btn.Test111.update')">修改</el-button>
    <el-button type="danger" v-if="$hasBp('btn.Test111.remove')">删除</el-button>
  </div>
</template>
<script>
export default {
  name: 'Test111',
  data() {
    return {
      
    };
  },
}
</script>

<style scoped>

</style>
