<template>
  <v-app>
    <v-container>
      <v-simple-table>
        <template v-slot:default>
          <thead>
            <tr>
              <th class="text-left">ID</th>
              <th class="text-left">NAME</th>
              <th class="text-left">EMAİL</th>
              <th class="text-left">WEBSİTE</th>
              <th class="text-left">COMPANY</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="user in users" :key="user.id">
              <td class="font-weight-bold">{{ user.id }}</td>
              <td class="text-xs-right">{{ user.name }}</td>
              <td class="text-xs-right">{{ user.email }}</td>
              <td class="text-xs-right">{{ user.website }}</td>
              <td class="text-xs-right">{{ user.company.name }}</td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-container>
  </v-app>
</template>

<script>
import axios from 'axios';

export default {
  name: "testView",
  data: () => ({
    users: null
  }),
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then(response => (this.users = response.data));
  }
}
</script>

<style scoped>

</style>