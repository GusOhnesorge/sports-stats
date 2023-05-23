<template>
  <div class="academic-fit-report">
    <AthleteHeader class="academic-fit-report__header" :athlete="athlete" />
    <div class="academic-fit-report__table">
      <StudentStatsTable :athlete="athlete" />
    </div>
  </div>
</template>
<script>
import AthleteHeader from "./header/AthleteHeader.vue";
import StudentStatsTable from "./student-stats/StudentStatsTable.vue";

export default {
  name: "AcademicFitReport",
  props: {
    athlete: {
      type: Object,
      required: false
    }
  },
  components: { AthleteHeader, StudentStatsTable }
};
</script>
<style scoped>
.academic-fit-report__header {
  margin-bottom: 3rem;
}
.academic-fit-report__table {
  margin-bottom: 6rem;
  display: block;
  overflow-x: auto;
  white-space: nowrap;
}
</style>
