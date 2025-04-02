<template>
  <div class="container">
    <h1>SmartWaste GIS</h1>
    <ClientOnly>
      <LeafletMap />
    </ClientOnly>
  </div>
</template>

<script>
import LeafletMap from "../components/LeafletMap.vue";
export default {
  name: "HomePage",
  components: {
    LeafletMap,
  },
};
</script>

<style scoped>
.container {
  text-align: center;
  padding: 20px;
}
</style>
