<template>
  <div class="card-container">
    <b-row>
      <b-col cols="12" align="center">
        <img src="../assets/logo.png" alt="">
        <p class="text-one"> Você está muito próximo de mudar a forma de </p>
        <p class="text-two"> hospedar seu site </p>
        <p class="text-three"> Escolha o seu plano </p>
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

.text-one {
  margin-top: 1rem !important;
  font-weight: bold !important;
  font-size: 1.9rem !important;
}

.text-two {
  color: #F30C6A !important;
  text-decoration: underline;
  font-size: 1.9rem !important;
  margin-top: -1.5rem !important;
}

.text-three {
  font-weight: normal;
  font-size: 1rem !important;
}


</style>
  