<template>
  <thead>
    <tr>
      <th v-if="stats[0].schoolName !== null" class="sticky-left" rowspan="2">
        School Name
      </th>
      <th v-if="stats[0].division !== null" rowspan="2">Athletic Div</th>
      <th v-if="stats[0].conference !== null" rowspan="2">Conference</th>
      <th v-if="stats[0].ranking !== null" rowspan="2">
        <div>Ranking*</div>
        <div>(DI NCAA)</div>
        <div>(DII & DIII Hero Sports)</div>
      </th>
      <th v-if="stats[0].gpa !== null" colspan="5">
        GPA
      </th>
      <th
        v-if="stats[0].sat !== null && stats[0].sat.reading !== null"
        rowspan="2"
      >
        <div>SAT Reading***</div>
        <div>25%-75%</div>
      </th>
      <th
        v-if="stats[0].sat !== null && stats[0].sat.math !== null"
        rowspan="2"
      >
        <div>SAT Math***</div>
        <div>25%-75%</div>
      </th>
      <th v-if="stats[0].act !== null" rowspan="2">
        <div>ACT Composite***</div>
        <div>25%-75%</div>
      </th>
    </tr>
    <tr v-if="stats[0].gpa !== null">
      <th>Min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>Max</th>
    </tr>
  </thead>
</template>
<script>
export default {
  name: "StudentsStatsTableHeader",
  props: {
    stats: {
      type: Array,
      required: true
    }
  }
};
</script>
<style scoped>
table th {
  text-align: center;
  background: var(--table-black);
  color: #fff;
}
</style>
