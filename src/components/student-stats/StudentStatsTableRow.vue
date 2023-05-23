<template>
  <tr>
    <td class="sticky-left">{{ stats.school }}</td>
    <td class="centered-text">{{ stats.division }}</td>
    <td>{{ stats.conference }}</td>
    <td class="centered-text">{{ stats.ranking }}</td>
    <td>{{ stats.gpa.min }}</td>
    <td>{{ stats.gpa["25%"] }}</td>
    <GPAColorColumn :school-gpa="stats.gpa['50%']" :student-gpa="gpa" />
    <td>{{ stats.gpa["75%"] }}</td>
    <td>{{ stats.gpa.max }}</td>
    <td class="centered-text">
      {{ stats.sat.reading.min }} - {{ stats.sat.reading.max }}
    </td>
    <td class="centered-text">
      {{ stats.sat.math.min }} - {{ stats.sat.math.max }}
    </td>
    <td class="centered-text">{{ stats.act.min }} - {{ stats.act.max }}</td>
  </tr>
</template>
<script>
import GPAColorColumn from "./GPAColorColumn.vue";
export default {
  name: "StudentStatsTableRow",
  props: {
    stats: {
      type: Object,
      required: true
    },
    gpa: {
      type: Number,
      required: true
    }
  },
  components: { GPAColorColumn }
};
</script>
<style scoped>
td {
  padding: 0.375rem;
  background-color: inherit;
}
</style>
