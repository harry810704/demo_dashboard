<template>
  <div class="home">
    <Sidebar />
    <div class="main">
      <router-view />
    </div>
  </div>
</template>

<script>
import Sidebar from "./components/Sidebar.vue";

export default {
  name: "App",
  components: {
    Sidebar,
  },
};
</script>

<style>
.home {
  display: flex;
  flex-direction: row;
}
.sidebar {
  width: 200px;
  background-color: #f7f7f7;
}

.main {
  flex: 1;
  margin-left: 200px;
  padding: 20px;
}
</style>
