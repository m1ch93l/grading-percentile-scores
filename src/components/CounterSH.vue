<template>
    <div class="text-center mt-3">
      <v-text-field class="align-items-center" width="300" v-model.number="inputNumber" label="Enter Total Items (SeniorHigh)"
        @input="updateCounter" />
    </div>
    <v-row>
      <v-col sm="6" md="4" lg="1" v-for="n in counter" :key="n">
        <v-card>
          <v-card-body>{{ n }} - {{ Math.round(((n - 0)) / inputNumber * 50 + 50) }}%</v-card-body>
        </v-card>
      </v-col>
    </v-row>
</template>

<script setup>
import { ref } from 'vue'

const counter = ref(0)
const inputNumber = ref(0)

function updateCounter() {
  counter.value = inputNumber.value
}
</script>
