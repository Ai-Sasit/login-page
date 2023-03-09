<template>
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
        label="Surname"
        density="compact"></v-text-field>
      <v-text-field
        color="white"
        variant="outlined"
        label="Lastname"
        density="compact"></v-text-field>
      <v-text-field
        color="white"
        label="Email"
        variant="outlined"
        type="email"
        density="compact"></v-text-field>
      <v-text-field
        color="white"
        label="Phone"
        variant="outlined"
        density="compact"></v-text-field>
      <v-select
        label="Gender"
        variant="outlined"
        density="compact"
        :items="['Girl', 'Man', 'Tree', 'Animal', 'Fly', 'Sleep']"></v-select>
    </v-card-text>

    <v-divider></v-divider>

    <v-card-actions>
      <v-spacer></v-spacer>

      <v-btn @click="$router.push('/')"> Save </v-btn>
    </v-card-actions>
  </v-card>
</template>
