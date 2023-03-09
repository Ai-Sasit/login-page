<template>
  <div>
    <v-row style="margin: 1rem">
      <v-col>
        <v-card>
          <v-table>
            <thead>
              <tr>
                <th class="text-left">Sequence</th>
                <th class="text-left">Thai Name</th>
                <th class="text-left">Eng Name</th>
                <th class="text-left">Country</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="i in item" :key="i.name">
                <td>{{ i.fields.sequences.stringValue }}</td>
                <td>{{ i.fields.thai_name.stringValue }}</td>
                <td>{{ i.fields.eng_name.stringValue }}</td>
                <td>{{ i.fields.country.stringValue }}</td>
              </tr>
            </tbody>
          </v-table>
        </v-card>
      </v-col>
      <v-col
        ><div>
          <v-card class="mx-auto mt-10" color="cyan-lighten-4" max-width="500">
            <v-toolbar flat color="cyan">
              <v-btn icon="mdi-account"></v-btn>

              <v-toolbar-title class="font-weight-light">
                User Profile
              </v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon>
                <v-fade-transition leave-absolute>
                  <v-icon>mdi-pencil</v-icon>
                </v-fade-transition>
              </v-btn>
            </v-toolbar>

            <v-card-text>
              <v-text-field
                color="white"
                variant="outlined"
                v-model="surname"
                label="Surname"
                density="compact"></v-text-field>
              <v-text-field
                color="white"
                variant="outlined"
                v-model="lastname"
                label="Lastname"
                density="compact"></v-text-field>
              <v-select
                label="Gender"
                variant="outlined"
                density="compact"
                v-model="country"
                :items="[
                  'Girl',
                  'Man',
                  'Tree',
                  'Animal',
                  'Fly',
                  'Sleep',
                ]"></v-select>
              <v-select
                label="Gender"
                variant="outlined"
                density="compact"
                :items="[
                  'Girl',
                  'Man',
                  'Tree',
                  'Animal',
                  'Fly',
                  'Sleep',
                ]"></v-select>
            </v-card-text>

            <v-divider></v-divider>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn @click="dialog = true"> add tour </v-btn>
              <v-btn @click="test"> add member </v-btn>
            </v-card-actions>
          </v-card>
        </div></v-col
      >
    </v-row>
  </div>
</template>
<script>
import { read_all_data, create_data } from "~~/services/configs";
import { group_members } from "~~/services/models";
export default {
  data() {
    return {
      surname: "",
      lastname: "",
      country: "",
      item: [],
      dialog: false,
    };
  },
  mounted() {
    read_all_data("deposit_invoice").then((result) => {
      this.item = result;
    });
  },
  methods: {
    test() {
      const id = [...Array(6)]
        .map(() => Math.floor(Math.random() * 16).toString(16))
        .join("");
      const payload = group_members(
        id,
        this.surname,
        this.lastname,
        this.country,
        id
      );

      create_data("deposit_invoice", payload).then((result) => {
        read_all_data("deposit_invoice").then((result) => {
          this.item = result;
        });
      });
    },
  },
};
</script>
