<template>
<div id="app">
  <Loading v-if='loading==true' />
  <Navbar :data="data" />
  <Controllers  :data="data" />
  <Models :data="data" />

</div>
</template>

<script>
import axios from 'axios'; // Импортируем axios для связи с Бэкендом

import Navbar from './components/navbar/Navbar'
import Controllers from './components/controller/Controllers'
import Models from './components/Models'
import Loading from './components/loading/Loading'


export default {
  name: 'App',
  components: {
    Loading,
    Navbar,
    Controllers,
    Models
  },
  data() {
    return {
      data: [], // Массив получаемых с сервера данных
      loading: true, //  Флажог для условной отрисовки при загрузке данных
    }
  },
  async mounted() { // Получаем JSON
    await axios.get('https://cors-anywhere.herokuapp.com/https://dh2.efir-net.ru/swagger/v2/swagger.json')
      .then(response => {
        this.data = response.data;
        this.loading = false;
      })

  }
}
</script>

<style lang="css" type="text/css">
  @import "./style/style.css";
</style>
