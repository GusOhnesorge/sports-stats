<template>
  <td class="gpa-color-column">{{ schoolGpa }}</td>
</template>
<script>
import {
  GpaVeryLow,
  GpaLow,
  GpaMedium,
  GpaHigh,
  GpaVeryHigh
} from "@/assets/styles/variables.module.css";
export default {
  name: "GPAColorColumn",
  props: {
    schoolGpa: {
      type: Number,
      required: true
    },
    studentGpa: {
      type: Number,
      required: true
    }
  },
  computed: {
    backgroundColor() {
      const gpaDif = this.schoolGpa - this.studentGpa;
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
    }
  }
};
</script>
<style scoped>
.gpa-color-column {
  background-color: v-bind(backgroundColor);
}
</style>
