<template>
  <div class="stats-report-footer">
    <p>
      *Rankings for Division I schools based on NCAA data (www.ncaa.com) and
      rankings for Division II & III schools are based on data from Hero Sports
      (www.herosports.com/rankings)
    </p>
    <p>
      ** GPA is based on SportsRecruits members who have shown interest in
      (favorited) the school and have provided their GPA on their profile
    </p>
    <p>
      ***SAT and ACT scores based on national data provided by the National
      Center of Education Statistics- https://nces.ed.gov/ipeds/
    </p>
  </div>
</template>
<script>
export default {
  name: "StatsReportFooter"
};
</script>
<style scoped>
.stats-report-footer {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
p {
  font-size: 0.62rem;
}
</style>
