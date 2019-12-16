<template >
  <section>
    <div class="controllers">
      <div v-for="(tag,index) in data.tags" :key="index">
        <Tags :tag='tag' :data='data' :showPosts='showPosts'/>
      </div>
    </div>
  </section>
</template>

<script>
import Tags from '../../components/controller/Tags.vue'

export default {
  components: {
    Tags
  },
  props: ['data'],
  name: 'Tags',
  data() {
    return {
      showPosts: false
    }
  }
}
</script>

<style scoped>
.controllers {
  margin: 20px 0 0 0;
}
</style>
