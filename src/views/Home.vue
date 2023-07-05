<template>
  <div class="container">
    <h1 class="mt-5">Home</h1>
    <table class="table table-striped table-bordered mt-5">
      <thead>
        <tr>
          <th>Name</th>
          <th>Status</th>
          <th>Time</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.id">
          <td>{{ item.name }}</td>
          <td>{{ item.status }}</td>
          <td>{{ item.time }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  data() {
    return {
      items: [
        { name: "Device 1", status: "Active", time: "10:30 AM" },
        { name: "Device 2", status: "Inactive", time: "9:45 AM" },
        { name: "Device 3", status: "Active", time: "8:20 AM" },
        { name: "Device 4", status: "Inactive", time: "7:55 AM" },
      ],
    };
  },
};
</script>

<style>
table {
  width: 100%;
  border-collapse: collapse;
}

th,
td {
  border: 1px solid #ccc;
  padding: 8px;
}

th {
  background-color: #ddd;
  color: #333;
  font-weight: bold;
}

.table-container {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
