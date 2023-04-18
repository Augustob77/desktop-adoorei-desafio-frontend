<template>
  <div>
    <div
      v-for="(planeItem, index) in planes"
      :key="index"
      class="component-card"
    >
      <card-plane
        :plane-item="planeItem"
      />
    </div>
  </div>
</template>
  
<script>
import CardPlane from '@/components/CardPlane.vue'
import planesList from '@/mixins/planesList'

export default {
  components: {
    CardPlane,
  },
  
  mixins: [planesList],

  data() {
    return {
      planes: planesList,
    }
  },
};
</script>
  