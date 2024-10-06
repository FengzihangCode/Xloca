<template>
  <div id="splash-screen" v-if="showSplashScreen" :class="themeClass">
    <img src="@/assets/logo.png" alt="App Logo" id="logo" />
  </div>
  <div v-else id="app-content">
    <!-- App主内容 -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      showSplashScreen: true,  // 控制是否显示启动页面
      themeClass: "light-theme",  // 可以根据用户系统或手动设置浅色/深色模式
    };
  },
  mounted() {
    // 模拟启动页面展示2秒后隐藏
    setTimeout(() => {
      this.showSplashScreen = false;
    }, 2000);
  },
};
</script>

<style>
/* 启动页面的样式 */
#splash-screen {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f1f1f1; /* Xcode浅色背景 */
  transition: opacity 0.5s ease-in-out;
}

.dark-theme {
  background-color: #1e1e1e; /* Xcode深色背景 */
}

#logo {
  width: 150px;
  height: 150px;
}

/* 主内容样式 */
#app-content {
  display: none;
}

</style>