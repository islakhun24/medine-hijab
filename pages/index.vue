<template>
  <div>
    <NavBar />
    <HomePage />
    <Footer />
  </div>
</template>

<script>
import NavBar from '../components/navbar.vue'
import HomePage from './home_page/index.vue'
import Footer from '../components/footer.vue'

export default {
  name: 'IndexPage',
  components: {
    HomePage,
    NavBar,
    Footer,
  },
}
</script>
