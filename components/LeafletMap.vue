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
        // Pastiin cuma jalan di client
        import("leaflet").then((L) => {
          import("leaflet/dist/leaflet.css"); // CSS-nya juga di-import dinamis
          const map = L.map("map").setView([-7.9535, 112.6145], 13); // Koordinat contoh
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
