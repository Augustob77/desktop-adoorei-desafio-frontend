<template>
  <div>
    <b-card
      class="d-flex justify-content-center align-items-center border-0"
      :title="planeItem.name"
    >
      <b-card-text class="price-text" align="center">
        {{ planeItem.price  }}
      </b-card-text>

      <b-card-text class="payment-desc-text" align="center">
        {{ planeItem.monthlyPaymentDescription  }}
      </b-card-text>
      
      <hr class="invoice-spacing">
      <b-card-text class="desc-text" align="center">
        {{ planeItem.description  }}
      </b-card-text>
      <hr class="invoice-spacing">

      <b-button
        class="my-3 border-0"
        type="button"
        block
        @click="selectPlane(planeItem)"
      >
        ESCOLHER ESSE PLANO
      </b-button>

      <b-card-text class="server-desc-text">
        {{ planeItem.serverDescription  }}
      </b-card-text>

      <div 
        v-for="(item, index) in planeItem.listOne"
        :key="index"
        align="left"
      >
        <b-card-text class="v-for-item-text">
          {{ '✔' + item }}
        </b-card-text>
      </div>

      <b-card-text class="generic-bold-text">
        {{ planeItem.support  }}
      </b-card-text>

      <b-card-text class="generic-bold-text">
        {{ planeItem.apps  }}
      </b-card-text>

      <div 
        v-for="(item, index) in planeItem.listTwo"
        :key="index"
        align="left"
      >
        <b-card-text class="v-for-item-text">
          {{ '✔' + item }}
        </b-card-text>
      </div>

      <b-card-text
        v-if="planeItem.migrationFree"
        class="generic-bold-text"
        align="left"
      >
        {{ planeItem.migrationFree }}
      </b-card-text>

      <b-card-text
        v-if="planeItem.migrationFreeText"
        align="left"
      >
        {{ '✔' + planeItem.migrationFreeText }}
      </b-card-text>

      <b-card-text class="generic-bold-text">
        {{ planeItem.youHave  }}
      </b-card-text>

      <div 
        v-for="(item, index) in planeItem.listTree"
        :key="index"
        align="left"
      >
        <b-card-text class="v-for-item-text">
          {{ '✔' + item }}
        </b-card-text>
      </div>
    </b-card>
  </div>
</template>

<script>
export default {
  props: {
    planeItem: {
      type: Object,
      default: () => {},
    }
  },

  data() {
    return {

    }
  },

  methods: {
    selectPlane(planeItem) {
      this.$router.push({
        name: 'register',
        params: { id: planeItem.id },
      })
    }
  }
}
</script>

<style scoped>

/* .plane-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: #f5f5f5 !important;
} */

.card-body {
  width: 21rem !important;
  padding: 3rem !important;
}

.card-title {
  font-size: 1.7rem;
  font-weight: bold;
  margin-left: 1.6rem;
  color: #545454;
}

.price-text {
  color: #F30C6A !important;
  font-size: 1.8rem;
  font-weight: bold;
  margin-top: 1rem;
}

.payment-desc-text {
  color: #7c7c7c !important;
  font-size: 1rem;
}

.desc-text {
  color: #545454 !important;
  font-size: 1.26rem;
}

.server-desc-text {
  margin-top: 0.6rem;
  font-weight: bold;
}

.generic-bold-text {
  margin-top: 1rem;
  font-weight: bold;
}

.v-for-item-text {
  margin-top: 0.3rem;
}

button {
  border-radius: 0.3rem !important;
  border: none;
  height: 4rem !important;
  width: 100%;
  font-size: 1.2rem !important;
  background-color: #F30C6A !important; 
  color: white;
}
</style>