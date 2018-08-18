<template>
    <li @click="del" :id="index">{{content}}</li>
</template>

<script>
export default {
  props:['index','content'],
  methods:{
      del(){
        this.$emit('remove',this.index);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
