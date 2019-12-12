<template>
  <section class="header__section">
    <div class="wrapper">
      <div class="logo">
        <img src="https://dh2.efir-net.ru/images/top-background.png" width="680px" height="120px">
      </div>
      <div class="header">
        <div class="header__title">
          <span class="snan__header__title">API Reference United Data (RU DATA) v2.0</span>
        </div>
        <div class="header__subtitle">
          <a href="http://developer.efir-net.ru/Documentation/RuData-API-v2.pdf">Краткое описание API 2.0</a>
          <a href="https://dh2.efir-net.ru/swagger/v2/swagger.json">Расширенное описание моделей данных</a>
        </div>
        <div class="header__footer">
          <div class="auto__button">
            <button type="button" class="button" @click="showModal">

              <span class="auto__span">
                Authorize
              </span>
              <img src="https://image.flaticon.com/icons/svg/240/240165.svg" width="20px" height="20px">
            </button>
            <ModalWindow v-show="isModalVisible" @close="closeModal" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ModalWindow from '../components/ModalWindow.vue'
export default {
  name: 'Navbar',
  components: {
    ModalWindow
  },
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
  text-align: center;
}

.header__title {
  text-align: center;
  font-weight: 700;
}

.header__subtitle {
  display: flex;
  flex-direction: column;
  margin-bottom: 40px;
}

.header__footer {
  padding: 40px 0;
}

.header__section {
  border-bottom: 1px solid rgba(0, 0, 0, .3);
}

.auto__button {
  display: flex;
  flex-direction: row-reverse;

}


.snan__header__title {
  font-size: 36px;
  color: #3b4151;
}
</style>
