<template>
  <div class="academic-fit-report">
    <AthleteHeader :athlete="athlete" />
  </div>
</template>

<script>
import AthleteHeader from "./AthleteHeader.vue";

export default {
  name: "AcademicFitReport",
  props: {
    athlete: {
      type: Object,
      required: false
    }
  },
  components: { AthleteHeader }
};
</script>
