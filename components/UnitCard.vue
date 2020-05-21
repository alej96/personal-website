<template>
  <router-link class="unit-link" :to="'/'">
    <div class="unit-card -shadow">
      <h4 class="title">{{ unit.FacilityName }}</h4>
      <h3 > {{ unit.LastName }}  	&nbsp; {{ unit.LastName}}</h3>
      <span class="eyebrow">  {{ unit.SpaceNumber}} &nbsp; </span>
      <span class="eyebrow">  $ {{ unit.SpacePrice}}</span>
      
      
    </div>
  </router-link>
</template>

<script>
export default {
  props: {
    unit: Object
  }
}
</script>

<style scoped>
.unit-card {
  padding: 20px;
  margin-bottom: 24px;
  transition: all 0.2s linear;
  cursor: pointer;
  background-color: rgb(223, 247, 247);
}
.unit-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(163, 132, 132, 0.2), 0 1px 15px 0 rgba(148, 132, 132, 0.19);
}
.unit-card > .title {
  margin: 0;
}
.unit-link{
  color: rgb(6, 126, 34);
  text-decoration: none;
  font-weight: 100;
}
</style>