<template>
  <section class="navbar__section">
    <div class="wrapper">
      <div class="logo">
        <img src="https://dh2.efir-net.ru/images/top-background.png" >
      </div>
      <div class="navbar">
        <div class="navbar__title">
          <span>API Reference United Data (RU DATA) v2.0</span>
        </div>
        <div class="navbar__link">
          <a href="http://developer.efir-net.ru/Documentation/RuData-API-v2.pdf">Краткое описание API 2.0</a>
          <a href="https://dh2.efir-net.ru/swagger/v2/swagger.json">Расширенное описание моделей данных</a>
        </div>
        <div class="navbar__footer">
          <div class="autorize__button">
            <button type="button" class="button" @click="showModal">

              <span class="autorize__span">
                Authorize
              </span>
              <img src="https://image.flaticon.com/icons/svg/240/240165.svg" width="20px" height="20px">
            </button>
            <ModalWindow :data='data' v-show="isModalVisible" @close="closeModal" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ModalWindow from '../../components/modalWindow/ModalWindow.vue'
export default {
  name: 'Navbar',
  components: {
    ModalWindow
  },
  props: ['data'],
  data() {
    return {
      isModalVisible: false,
    }
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.logo {
  max-width: 680px;
  height: 120px;
  text-align: center;
}

.navbar {
  margin: 50px 0px 20px 0;
  width: 100%;
  height: 5%;
  overflow: hidden;
  box-sizing: border-box;
}

.navbar__title {
  text-align: center;
  font-weight: 700;
  font-size: 36px;
  color: #3b4151;
}

.navbar__link {
  display: flex;
  flex-direction: column;
  margin-bottom: 40px;
}

.navbar__footer {
  padding: 40px 0;
}

.navbar__section {
  border-bottom: 1px solid rgba(0, 0, 0, .3);
}

.autorize__button {
  display: flex;
  flex-direction: row-reverse;

}

.autorize__span {
  float: left;
  padding: 4px 10px 0 4px;
}

</style>
