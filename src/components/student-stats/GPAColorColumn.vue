<script setup>
import { computed } from "vue";
import {
  GpaVeryLow,
  GpaLow,
  GpaMedium,
  GpaHigh,
  GpaVeryHigh
} from "@/assets/styles/variables.module.css";
const props = defineProps({
  schoolGpa: {
    type: Object,
    required: true
  },
  studentGpa: {
    type: Object,
    required: true
  }
});
const schoolGpa = computed(() => props.schoolGpa);
const studentGpa = computed(() => props.studentGpa);
const backgroundColor = computed(() => {
  const gpaDif = schoolGpa.value - studentGpa.value;
  if (gpaDif >= 0.1) {
    return GpaVeryLow;
  } else if (gpaDif > 0) {
    return GpaLow;
  } else if (gpaDif <= -0.1) {
    return GpaVeryHigh;
  } else if (gpaDif < 0) {
    return GpaHigh;
  }
  return GpaMedium;
});
</script>
<template>
  <td class="gpa-color-column">{{ schoolGpa }}</td>
</template>
<style scoped>
.gpa-color-column {
  background-color: v-bind(backgroundColor);
}
</style>
