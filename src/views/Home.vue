<template>
  <div class="home">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <todo/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import todo from '@/components/todo.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,todo
  }
}
</script>
