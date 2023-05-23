<script setup>
import { computed } from "vue";
import PlaceholderColors from "@/assets/placeholder-colors.json";

const props = defineProps({
  student: {
    type: Object,
    required: true
  }
});
const student = computed(() => props.student);
const studentInitials = computed(() => {
  const names = student.value.name.split(" ");
  return names.reduce((prevInitials, name) => prevInitials + name[0], "");
});
const initialsColor = computed(() => {
  const calculatedColorIndex =
    studentInitials.value.slice(-1).charCodeAt(0) % 6;
  return PlaceholderColors.colors[calculatedColorIndex];
});
</script>
<template>
  <div class="student-image">
    <img v-if="false" :src="student.profile_image" />
    <div class="student-image__initials" v-else>{{ studentInitials }}</div>
  </div>
</template>
<style scoped>
.student-image {
  --background-color: v-bind("initialsColor");
  height: 5rem;
  width: 5rem;
  font-size: 2rem;
  border-radius: 50%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  background-color: var(--background-color);
}
.student-image img {
  height: 100%;
}
</style>
