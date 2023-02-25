<script setup>
import DashboardApp from '@/components/dashboard/DashboardApp.vue';
import dashboardData from '@/data/data.json';
</script>

<template>
  <main>
    <DashboardApp :data="dashboardData"/>
  </main>
</template>

<style scoped>

</style>
