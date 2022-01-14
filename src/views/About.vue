<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h2>{{name}}</h2>
    <h2>{{age}}</h2>
  </div>
</template>
<script>
export default{
    data(){
        return {
          name: 'Nazar',
        age:23
      }
    }
  }
</script>
<style scoped>
h1{
  color:green;
}
</style>