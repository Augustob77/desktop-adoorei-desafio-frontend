<template>
  <div class="card-container">
    <b-row>
      <b-col>
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
        planeItem: null,
      }
    },
  
    mounted() {
      const { id } = this.$router.currentRoute.params
      this.planeItem = planesList.find(item => item.id === id)
    }
}
</script>

<style scoped>
.card-container {
  display: flex;
  height: 100%;
  justify-content: center;
  padding: 6rem;
  background-color: #f5f5f5 !important;
}

</style>