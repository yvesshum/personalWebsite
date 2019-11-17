<template>
  <div class="home">
    <h1>Home page</h1>
    
  </div>
</template>


<script>

export default {
  name: 'home',
  components: {

  },
  data() {
    return {

    }
  },

  methods: {
    handleOpen(key, keyPath) {
        console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
}
</script>

<style lang='scss'>
  .home {
    background-color: #121212;
    height: 100%;
    width: 100%;
  }
  
</style>
