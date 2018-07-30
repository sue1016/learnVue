<template>
<li @click='handleDelete'>{{itemContent}}</li>
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
<style scoped>

</style>
