<script setup>
import AthleteHeader from "./header/AthleteHeader.vue";
import StudentStatsTable from "./student-stats/StudentStatsTable.vue";
import StatsReportFooter from "./StatsReportFooter.vue";

defineProps({
  athlete: {
    type: Object,
    required: false
  }
});
</script>
<template>
  <div class="academic-fit-report">
    <hr />
    <AthleteHeader :athlete="athlete" />
    <div class="academic-fit-report__table">
      <StudentStatsTable :athlete="athlete" />
    </div>
    <StatsReportFooter />
    <hr />
  </div>
</template>
<style scoped>
.academic-fit-report {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
.academic-fit-report__table {
  margin-bottom: 2rem;
  padding-bottom: 0.5rem;
  display: block;
  overflow-x: auto;
  white-space: nowrap;
}
hr {
  width: 100%;
  border: 0.25rem solid var(--bright-blue);
}
</style>
