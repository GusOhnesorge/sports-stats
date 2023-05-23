<template>
  <table id="stats-table">
    <colgroup span="5"></colgroup>
    <StudentStatsTableHeader :stats="athlete.report" />
    <tbody>
      <StudentStatsTableRow
        v-for="report in athlete.report"
        :stats="report"
        :gpa="athlete.gpa"
      />
    </tbody>
  </table>
</template>
<script>
import StudentStatsTableHeader from "./StudentStatsTableHeader.vue";
import StudentStatsTableRow from "./StudentStatsTableRow.vue";

export default {
  name: "StudentsStatsTable",
  props: {
    athlete: {
      type: Object,
      required: true
    }
  },
  components: { StudentStatsTableHeader, StudentStatsTableRow }
};
</script>
<style scoped>
table {
  font-size: 0.5625rem;
  border-collapse: collapse;
  width: 100%;
}
tr:nth-child(odd) {
  background-color: white;
}
tr:nth-child(even) {
  background-color: var(--table-light-blue);
}
</style>
