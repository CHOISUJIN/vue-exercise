<template>
<div class="clearAllContainer">
  <span class="clearAllBtn" v-on:click="RemoveAll">Remove All</span>
</div>
</template>

<script>

export default{
  methods:{
    RemoveAll() {
      this.$emit("RemoveAll");
    }
  }
}

</script>

<style scoped>
  .clearAllContainer{cursor: pointer;width:8.5rem;height: 50px;line-height: 50px;background-color: white;border-radius: 5px; margin: 0 auto;}
  .clearAllBtn{color: #e20303;display: block;}
</style>
