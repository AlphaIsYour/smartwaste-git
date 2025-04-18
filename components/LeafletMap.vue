<template>
  <div id="map" class="map"></div>
</template>

<script>
import { onMounted } from "vue";

export default {
  name: "LeafletMap",
  setup() {
    onMounted(() => {
      if (import.meta.client) {
        import("leaflet").then((L) => {
          import("leaflet/dist/leaflet.css");
          const map = L.map("map").setView([-7.9535, 112.6145], 13);
          L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
            attribution:
              '© <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a>',
          }).addTo(map);
        });
      }
    });
  },
};
</script>

<style scoped>
.map {
  width: 100%;
  height: 400px;
}
</style>
