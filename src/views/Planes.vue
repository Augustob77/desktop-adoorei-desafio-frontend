<template>
  <div class="card-container">
    <b-row>
      <b-col cols="12" align="center">
        <img src="../assets/logo.png" alt="">
      </b-col>
      <b-col
        v-for="planeItem in planes"
        :key="planeItem.id"
      >
        <card-plane
          :plane-item="planeItem"
        />
      </b-col>
    </b-row> 
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

<style scoped>
.card-container {
  display: flex;
  height: 100%;
  justify-content: center;
  padding: 6rem;
  background-color: #f5f5f5 !important;
}

img {
  width: 250px;
}


</style>
  