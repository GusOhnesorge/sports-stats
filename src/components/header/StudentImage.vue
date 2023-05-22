<template>
  <div class="student-image">
    <img v-if="false" :src="student.profile_image" />
    <div class="student-image__initials" v-else>{{ studentInitials }}</div>
  </div>
</template>
<script>
import PlaceholderColors from "@/assets/placeholder-colors.json";

export default {
  name: "StudentImage",
  props: {
    student: {
      type: Object,
      required: true
    }
  },
  computed: {
    studentInitials() {
      const names = this.student.name.split(" ");
      return names.reduce((prevInitials, name) => prevInitials + name[0], "");
    },
    initialsColor() {
      const calculatedColorIndex = this.student.name.charCodeAt(0) % 6;
      return PlaceholderColors.colors[calculatedColorIndex];
    }
  }
};
</script>
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
