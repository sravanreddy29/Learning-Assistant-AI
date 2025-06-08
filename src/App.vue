<template>
  <v-app>
    <v-main class="d-flex justify-center align-center">
      <v-container max-width="500">
        <v-card class="pa-4" elevation="6">
          <v-card-title class="text-h5">📚 Daily Learning Bot</v-card-title>

          <v-card-text>
            <v-select
              label="Choose a Topic"
              :items="topics"
              v-model="selectedTopic"
              outlined
            ></v-select>

            <v-text-field
              v-model="reminderTime"
              label="Reminder Time"
              type="time"
              outlined
            ></v-text-field>
          </v-card-text>

          <v-card-actions>
            <v-btn color="primary" @click="savePreferences" block>Start Learning</v-btn>
          </v-card-actions>

          <v-alert
            type="success"
            class="mt-4"
            v-if="confirmation"
            density="compact"
          >
            Preferences saved! You'll start receiving daily learning content.
          </v-alert>
        </v-card>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'

const topics = ['Vocabulary', 'Finance', 'Random Facts']
const selectedTopic = ref('Vocabulary')
const reminderTime = ref('08:00')
const confirmation = ref(false)

function savePreferences() {
  // TODO: send data to backend
  confirmation.value = true
}
</script>
