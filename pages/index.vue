<template>
  <v-row style="margin: 1rem">
    <v-col>
      <v-card>
        <v-table>
          <thead>
            <tr>
              <th class="text-left">Name</th>
              <th class="text-left">Lastname</th>
              <th class="text-left">Email</th>
              <th class="text-left">Phone</th>
              <th class="text-left">Sex</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in desserts" :key="item.name">
              <td>{{ item.name }}</td>
              <td>{{ item.lastname }}</td>
              <td>{{ item.email }}</td>
              <td>{{ item.phone }}</td>
              <td>{{ item.sex }}</td>
            </tr>
          </tbody>
        </v-table>
      </v-card>
    </v-col>
    <v-col>
      <v-btn @click="$router.push('home')">Register</v-btn>
    </v-col>
  </v-row>
</template>
<script>
export default {
  data() {
    return {
      desserts: [
        {
          name: "Frozen",
          lastname: "Yogurt",
          email: "yog@hot.co",
          phone: "02145478554",
          sex: "men",
        },
        {
          name: "Frozen",
          lastname: "Yogurt",
          email: "yog@hot.co",
          phone: "02145478554",
          sex: "men",
        },
        {
          name: "Frozen",
          lastname: "Yogurt",
          email: "yog@hot.co",
          phone: "02145478554",
          sex: "men",
        },
        {
          name: "Frozen",
          lastname: "Yogurt",
          email: "yog@hot.co",
          phone: "02145478554",
          sex: "men",
        },
        {
          name: "Frozen",
          lastname: "Yogurt",
          email: "yog@hot.co",
          phone: "02145478554",
          sex: "men",
        },
      ],
    };
  },
};
</script>
