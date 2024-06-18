<template>
  <div>
    <nav :class="navClass">
      <div class="container">
        <a class="navbar-brand" href="/">
          <img
            src="../assets/logo_product.png"
            width="100px"
            alt="logo aileen"
          />
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <i class="fas fa-bars"></i>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mr-auto w-100 justify-content-end">
            <li class="nav-item active">
              <a class="nav-link" href="/" @click="setActive(0)"
                >Home <span class="sr-only">(current)</span></a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#product" @click="setActive(1)"
                >Product</a
              >
            </li>

            <li class="nav-item">
              <a class="nav-link cursor-pointer" @click="showModal">Contact</a>
            </li>

            <li class="nav-item">
              <a class="nav-link" href="#description" @click="setActive(3)"
                >Description</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <modalReg />
  </div>
</template>

<script>
import modalReg from '../pages/form_page/form_page.vue'
export default {
  components: { modalReg },
  data() {
    return {
      isScrolled: false,
    }
  },
  mounted() {
    this.checkRouteAndSetActive()
    window.addEventListener('scroll', this.handleScroll)
  },
  computed: {
    navClass() {
      return this.isScrolled
        ? 'navbar navbar-expand-lg fixed-top navbar-white'
        : 'navbar navbar-expand-lg fixed-top navbar-transparent'
    },
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    setActive(index) {
      var navItems = document.querySelectorAll('.nav-item')
      navItems.forEach(function (item) {
        item.classList.remove('active')
      })
      navItems[index].classList.add('active')
    },
    showModal() {
      const modalElement = document.getElementById('exampleModal')
      const modal = new bootstrap.Modal(modalElement)
      modal.show()
    },
    checkRouteAndSetActive() {
      switch (this.$route.fullPath) {
        case '/#product':
          this.setActive(1)
          break
        case '/#description':
          this.setActive(3)
          break
        default:
          this.setActive(0)
          break
      }
    },
    handleScroll() {
      this.isScrolled = window.scrollY > window.innerHeight
    },
  },
}
</script>

<style scoped>
.navbar-transparent {
  background-color: transparent !important;
  transition: background-color 0.3s ease;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}
.navbar-white {
  background-color: #fff !important;
  transition: background-color 0.3s ease;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
}

.active a.nav-link {
  color: #0056b3;
}
.nav-item {
  position: relative;
}

.nav-item.active::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 50%;
  height: 2px;
  background-color: #0056b3;
  animation: underline 0.3s ease;
}

@keyframes underline {
  from {
    width: 0;
  }
  to {
    width: 50%;
  }
}
@media (max-width: 991px) {
  .nav-item.active::after {
    width: 5%;
  }

  @keyframes underline {
    from {
      width: 0;
    }
    to {
      width: 5%;
    }
  }
}
</style>
