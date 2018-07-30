<template>
<li class='item' @click='handleDelete'>{{itemContent}}</li>
</template>

<script>
export default {
  props: ['itemContent','index'],
  methods: {
    handleDelete: function(){
      this.$emit('delete',this.index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- 加scoped是局部样式，不加是全局样式 -->
<!-- 一般都加scoped -->
<style scoped>
.item{
  color: green;
}
</style>
