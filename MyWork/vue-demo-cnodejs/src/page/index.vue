<template>
  <div>
    <Header></Header>
    <div class="article_list">
      <ul>
        <li v-for="(value, key) in list" :key="key.value">
          {{ key }}: {{value}}
        </li>
      </ul>
    </div>
    <Footer></Footer>
  </div>
</template>
<script>
import Header from '../components/header.vue'
import Footer from '../components/footer.vue'
export default {
  components: { Header, Footer },
  data () {
    return {
      list: [ ]
    }
  },
  created () {
    this.getData()
  },
  methods: {
    getData () {
      this.$api.get('baseinfo?name=北京百度网讯科技有限公司', null, r => {
        this.list = r.result
        console.log(this.list)
      })
    }
  }
}
</script>
