<template>
  <div class="container">
    <h1 class="mt-5">Products Page</h1>
    <table class="table table-striped table-bordered mt-5">
      <thead>
        <tr>
          <th>Device name</th>
          <th>Status</th>
          <th>Control</th>
          <th>IP address</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(device, index) in devices" :key="index">
          <td>{{ device.name }}</td>
          <td>{{ device.status }}</td>
          <td>
            <button @click="device.control = !device.control">
              {{ device.control ? "Stop" : "Start" }}
            </button>
          </td>
          <td>{{ device.ip }}</td>
        </tr>
      </tbody>
    </table>

    <table>
      <thead>
        <tr>
          <th>Alarm information</th>
          <th>Status</th>
          <th>Trigger time</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(alarm, index) in alarms" :key="index">
          <td>{{ alarm.info }}</td>
          <td>{{ alarm.status }}</td>
          <td>{{ alarm.triggerTime }}</td>
        </tr>
      </tbody>
    </table>

    <form @submit.prevent="addDevice">
      <h3>Add Device</h3>
      <div class="row">
        <div class="col">
          <label for="device-name">Device name:</label>
          <input type="text" id="device-name" v-model="newDeviceName" required>
        </div>
        <div class="col">
          <label for="ip-address">IP address:</label>
          <input type="text" id="ip-address" v-model="newDeviceIP" required>
        </div>
        <div class="col">
          <label for="port-number">Port number:</label>
          <input type="text" id="port-number" v-model="newDevicePort" required>
        </div>
        <div class="col">
          <button class="btn btn-primary" type="submit">Add</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "ProductsList",
  data() {
    return {
      devices: [
        { name: "Device A", status: "Running", control: false, ip: "192.168.0.1" },
        { name: "Device B", status: "Stopped", control: true, ip: "192.168.0.2" },
        { name: "Device C", status: "Running", control: false, ip: "192.168.0.3" },
      ],
      alarms: [
        { info: "Alarm A", status: "Active", triggerTime: "2022-12-25 12:00" },
        { info: "Alarm B", status: "Resolved", triggerTime: "2022-12-31 12:00" },
        { info: "Alarm C", status: "Active", triggerTime: "2023-01-01 00:00" },
      ],
      newDeviceName: "",
      newDeviceIP: "",
      newDevicePort: "",
    };
  },
  methods: {
    addDevice() {
      const newDevice = {
        name: this.deviceName,
        ipAddress: this.ipAddress,
        port: this.portNumber,
      };
      // do something with newDevice
      this.devices.push(newDevice);
      // reset form
      this.deviceName = "";
      this.ipAddress = "";
      this.portNumber = "";
    },
  },
};
</script>
