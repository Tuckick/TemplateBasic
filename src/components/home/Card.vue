<template>
  <v-row class="mt-5 mx-2">
    <v-col v-for="item in list" :key="item.title" cols="12" md="4">
      <v-card link class="h-100">
        <template v-slot:title>
          <img
            v-if="item.icon == 'devices'"
            src="`../../assets/icons/card/devices.svg`"
            alt="devices"
          />
          <img
            v-if="item.icon == 'home_iot_device'"
            src="`../../assets/icons/card/home_iot_device.svg`"
            alt="home_iot_device"
          />
          <img
            v-if="item.icon == 'lab_research'"
            src="`../../assets/icons/card/lab_research.svg`"
            alt="lab_research"
          />
          <br />
          <span class="font-weight-black">{{ item.title }}</span>
        </template>

        <v-card-text class="bg-surface-light pt-4 h-100">
          {{ item.desc }}
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script setup>
import { ref } from "vue";
const list = ref([
  {
    title: "Website",
    desc: "responsive design, high performance and SEO friendly.",
    icon: "devices",
  },
  {
    title: "IOT",
    desc: "real-time data, monitoring and control.",
    icon: "home_iot_device",
  },
  {
    title: "Project",
    desc: "modern and practical solutions.",
    icon: "lab_research",
  },
]);
</script>