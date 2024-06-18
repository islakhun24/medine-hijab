<template>
  <div class="home_page">
    <section_1 />
    <section_2 />
    <section_3 />
    <section_4 />
    <modalForm />
  </div>
</template>

<script>
import section_1 from './section_1.vue'
import section_2 from './section_2.vue'
import section_3 from './section_3.vue'
import section_4 from './section_4.vue'
import modalForm from '../form_page/form_page.vue'

export default {
  components: {
    section_1,
    section_2,
    section_3,
    section_4,
    modalForm,
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      const scrollPosition = window.scrollY || window.pageYOffset
      const viewportHeight = window.innerHeight

      if (scrollPosition >= viewportHeight) {
        this.showModal()
        window.removeEventListener('scroll', this.handleScroll)
      }
    },
    showModal() {
      const modalElement = document.getElementById('exampleModal')
      const modal = new bootstrap.Modal(modalElement)
      modal.show()
    },
  },
}
</script>
