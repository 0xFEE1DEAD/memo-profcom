<template>
  <l-map ref="map" v-model:zoom="zoom" :center="[52.25010, 104.26354]">
    <l-tile-layer
      url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
      layer-type="base"
      name="OpenStreetMap"
    ></l-tile-layer>

    <l-marker :lat-lng="[52.25010, 104.26354]">
        <l-tooltip :options="{'permanent': true}">
            <div style="font-family: 'Bebas Neue'; font-weight: 400; font-size: 20px;">
                {{locationString}}
            </div>
        </l-tooltip>
    </l-marker>
  </l-map>
</template>
<script>
import { LMap, LTileLayer, LMarker, LTooltip } from "@vue-leaflet/vue-leaflet";
import "leaflet/dist/leaflet.css";

export default {
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LTooltip
  },
  props: {
      locationString: {
          type: String
      }
  },
  data() {
    return {
      zoom: 15,
    };
  },
};
</script>

<style></style>