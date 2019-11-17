<template>
  <div class="app">
    <div v-if="this.$route.name !== 'start'">
      <div class="sidebar">
        <el-menu
          default-active="/home"
          class="el-menu-vertical"
          @open="handleOpen"
          @close="handleClose"
          background-color="#121212"
          text-color="#ffffff"
          active-text-color="#bb86fc"
          stlye="height: 100vh"
          :router="true"
          :collapse="isCollapse"
        >
          <el-menu-item index="/home">
            <i class="el-icon-s-home"></i>
            <span>Home</span>
          </el-menu-item>
          <el-menu-item index="/about">
            <i class="el-icon-info"></i>
            <span>About</span>
          </el-menu-item>
          <el-menu-item index="/Projects">
            <i class="el-icon-data-board"></i>
            <span>Projects</span>
          </el-menu-item>
          <el-menu-item index="/Contact">
            <i class="el-icon-user-solid"></i>
            <span>Contact</span>
          </el-menu-item>
        </el-menu>
      </div>
      <div v-bind:class="{ contentCollapsedSidebar: isCollapse, contentOpenSidebar: !isCollapse}">
        <router-view/>
      </div>
    </div>
    <router-view v-else/>  
    
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      isCollapse: true,
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

<style lang="scss">
.app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #121212;

  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.el-menu-vertical:not(.el-menu--collapse) {
    width: 200px;
    height: 100vh;
}
.el-menu-vertical{
    width: 50;
    height: 100vh;
}

.sidebar{ 
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
}

.contentCollapsedSidebar{
  padding-left: 50;
  padding: 0px 10px;
}
.contentOpenSidebar{
  padding-left: 200;
  padding: 0px 10px;
}

</style>
