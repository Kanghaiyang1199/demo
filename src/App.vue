<template>
  <div id="app">
    <header class="header">
      <h1>Vue2 + Router + ECharts</h1>
      <nav>
        <router-link to="/">首页</router-link>
        <router-link to="/chart">图表示例</router-link>
      </nav>
    </header>
    <main>
      <router-view />
    </main>
  </div>
</template>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin: 0 auto;
  max-width: 960px;
  padding: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
}

nav a {
  margin-left: 16px;
  color: #409eff;
  text-decoration: none;
}

nav a.router-link-exact-active {
  font-weight: bold;
}
</style>
