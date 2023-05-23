<template>
  <div class="athlete-header">
    <div class="athlete-header__student">
      <StudentImage :student="athlete" />
      <div class="athlete-header__student__overview">
        <h2>{{ athlete.name }}</h2>
        <div class="athlete-header__student__info">
          <p><span class="bold">Sport:</span> {{ athlete.sport }}</p>
          <p><span class="bold">Class:</span> {{ athlete.grad_year }}</p>
          <p><span class="bold">Club:</span> {{ athlete.club.name }}</p>
          <p>
            <span class="bold">High School:</span>
            {{ athlete.high_school.name }}
          </p>
          <p><span class="bold">GPA:</span> {{ athlete.gpa }}</p>
          <p><span class="bold">Desired Major:</span> {{ athlete.major }}</p>
        </div>
      </div>
    </div>
    <div class="athlete-header__logo">
      <img src="@/assets/sr-insights-logo.png" />
      <p>Academic Fit Report</p>
    </div>
  </div>
</template>
<script>
import StudentImage from "./StudentImage.vue";
export default {
  name: "AcamdemicHeader",
  props: {
    athlete: {
      type: Object,
      required: true
    }
  },
  components: { StudentImage }
};
</script>
<style>
.athlete-header {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap-reverse;
  gap: 1rem;
}
.athlete-header__student {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}
.athlete-header__student h2 {
  font-size: 1rem;
  color: var(--bright-blue);
  padding: 0;
  margin: 0;
}
.athlete-header__student__overview {
  display: flex;
  flex-direction: column;
  height: 4rem;
}
.athlete-header__student__info {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  height: 100%;
  gap: 0.1875rem 2rem;
  font-size: 0.75rem;
}
.athlete-header__logo {
  display: flex;
  flex-direction: column;
  align-items: end;
  font-size: 0.875rem;
}
.athlete-header__logo img {
  height: 2.5rem;
}
@media only screen and (max-width: 769px) {
  .athlete-header {
    justify-content: center;
  }
  .athlete-header__student__overview {
    height: auto;
  }
  .athlete-header__logo {
    align-items: center;
  }
}
</style>
