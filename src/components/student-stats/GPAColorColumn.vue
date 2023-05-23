<template>
  <td>{{ schoolGpa["50%"] }}</td>
</template>
<script>
export default {
  name: "GPAColorColumn",
  props: {
    schoolGpa: {
      type: Object,
      required: true
    },
    studentGpa: {
      type: Object,
      required: true
    }
  }
};
</script>
<style scoped></style>
