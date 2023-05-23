<script setup>
import AcademicFitReport from "@/components/AcademicFitReport.vue";
import AthleteData from "@/assets/data.json";
import { ref } from "vue";
const athlete_info = ref(AthleteData.data[0]);
</script>
<template>
  <div class="container">
    <AcademicFitReport :athlete="athlete_info" />
  </div>
</template>
<style>
@import "./assets/styles/_variables.css";
</style>
