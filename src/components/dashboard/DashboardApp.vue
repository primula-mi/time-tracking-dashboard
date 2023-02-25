<script setup>
import InfoCard from '@/components/InfoCard/InfoCard.vue';
import ViewSelectorList from '@/components/InfoCard/ViewSelectorList.vue';
import TrackingCard from '@/components/TrackingCard/TrackingCard.vue';
import {ref} from "vue";

const props = defineProps(["data"]);
let activeView = ref("daily");
</script>

<template>
  <section class="dashboard">
    <div class="dashboard__content">
      <aside class="dashboard__person">
        <InfoCard />
        <ViewSelectorList @chageView="activeView=$event.toLowerCase()"/>
      </aside>
      <div
      class="dashboard__item"
      v-for="activity, idx in props.data"
      :key="idx"
      
      :class="`dashboard__item--${activity.title.replace(' ', '-').toLowerCase()}`"
      >
        <TrackingCard :title="activity.title" :timeframes="activity.timeframes" :view="activeView"/>
      </div>
    </div>
  </section>
</template>

<style scoped>
.dashboard {
  min-height: 100vh;
  padding: 4rem 0 0.5rem;

  display: flex;
  justify-content: center;
  align-items: center;
}
.dashboard__content {
  width: 100%;
  max-width: 900px;
  margin: 0 auto;

  display: grid;
  gap: 1.5rem;
  justify-content: center;
  grid-template-columns: repeat(1, minmax(300px, 330px));
}

.dashboard__person {
  width: 100%;
  background: var(--blue-800);
  border-radius: var(--radii);
}

.dashboard__item {
  width: 100%;
  padding: 2.15rem 0 0;
  background: #fff;
  border-radius: var(--radii);

  background-repeat: no-repeat;
  background-position: 92% -8%;
}
.dashboard__item:hover .tracking-card{
  background-color: var(--blue-500);
}
.dashboard__item--work {
  background-image: url(@/assets/imgaes/icon-work.svg);
  background-color: var(--red-100);
}
.dashboard__item--play {
  background-image: url(@/assets/imgaes/icon-play.svg);
  background-color: var(--blue-100);
}
.dashboard__item--study {
  background-image: url(@/assets/imgaes/icon-study.svg);
  background-color: var(--red-200);
}
.dashboard__item--exercise {
  background-image: url(@/assets/imgaes/icon-exercise.svg);
  background-color: var(--green-100);
}
.dashboard__item--social {
  background-image: url(@/assets/imgaes/icon-social.svg);
  background-color: var(--violet-500);
}
.dashboard__item--self-care {
  background-image: url(@/assets/imgaes/icon-self-care.svg);
  background-color: var(--orange-100);
}

@media (min-width: 1024px) {
  .dashboard__content {
    grid-template-columns: repeat(4, 1fr);
  }
  .dashboard__person {
    grid-row-start: 1;
    grid-row-end: 3;
    grid-column-start: 1;
    grid-column-end: 2;
    height: 100%;

    display: flex;
    flex-direction: column;
  }
}

</style>