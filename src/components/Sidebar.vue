<template>
  <div class="sidebar">
    <div class="sidebar-header">
      <h3>Dashboard</h3>
    </div>
    <ul class="nav flex-column">
      <li class="nav-item">
        <router-link to="/" active-class="active">
          <i class="fa fa-home"></i> Home
        </router-link>
      </li>
      <li class="nav-item">
        <router-link to="/products" active-class="active">
          <i class="fa fa-product-hunt"></i> Products
        </router-link>
      </li>
      <li class="nav-item">
        <router-link to="/orders" active-class="active">
          <i class="fa fa-shopping-cart"></i> Orders
        </router-link>
      </li>
      <li class="nav-item">
        <router-link to="/customers" active-class="active">
          <i class="fa fa-users"></i> Customers
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
}
</script>

<style scoped>
.sidebar {
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  width: 200px;
  background-color: #333;
  color: #fff;
}

.sidebar-header {
  height: 50px;
  background-color: #222;
  display: flex;
  align-items: center;
  justify-content: center;
}

.sidebar ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.sidebar li {
  padding: 10px;
  border-bottom: 1px solid #444;
}

.sidebar li:last-child {
  border-bottom: none;
}

.sidebar a {
  display: flex;
  align-items: center;
  color: #fff;
  text-decoration: none;
}

.sidebar a i {
  font-size: 20px;
  margin-right: 10px;
}

.sidebar a.active {
  background-color: #444;
}
</style>
