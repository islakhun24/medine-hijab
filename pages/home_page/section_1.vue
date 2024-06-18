<template>
  <div class="section_1">
    <div class="container">
      <div class="content_1">
        <div class="model_content">
          <p class="text-center text_content_1 fadeIn third">
            <i>MEDINE HIJAB</i>
          </p>
          <img
            src="../../assets/hijab_model.png"
            alt="image content"
            class="responsive fadeIn first"
          />
        </div>
        <div @click="scrollToSection" class="cursor-pointer">
          <div class="scroll-btn">
            <small>
              <span>&RightAngleBracket;</span>
              <span>&RightAngleBracket;</span>
              <span>&RightAngleBracket;</span>
            </small>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'section_1',
  methods: {
    scrollToSection() {
      this.$router.push({ path: '/', hash: '#product' }).then(() => {
        const section = document.getElementById('product')
        if (section) {
          section.scrollIntoView({ behavior: 'smooth' })
        }
      })
    },
  },
}
</script>

<style scoped>
.section_1 {
	background: linear-gradient(-45deg, #23a6d5, #23d5ab, #23a6d5, #23d5ab);
	background-size: 400% 400%;
	animation: gradient 15s ease infinite;
	/* height: 100vh; */
}

@keyframes gradient {
	0% {
		background-position: 0% 50%;
	}
	50% {
		background-position: 100% 50%;
	}
	100% {
		background-position: 0% 50%;
	}
}
.responsive {
  width: 100%;
  height: auto;
}
.content_1 {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.model_content {
  /* background-image: url('../../assets/bg_content.png'); */
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  /* z-index: -2; */
}
.responsive {
  z-index: 1;
  box-shadow: 0 1px 2px -2px rgba(0, 0, 0, 0.16),
    0 3px 6px 0 rgba(0, 0, 0, 0.12), 0 5px 12px 4px rgba(0, 0, 0, 0.09);
}
.text_content_1 {
  font-family: 'Poppins';
  font-weight: 700;
  position: relative;
  /* z-index: -1; */
  color: #fff;
  text-shadow: 5px 5px 10px #000;
}

/* Animation arrow */

.scroll-btn {
  position: absolute;
  left: 50%;
  bottom: 5px;
  transform: translateX(-50%);
}
.scroll-btn small {
  text-decoration: none;
  display: inline-block;
  font-size: 3em;
  font-weight: bold;
  color: #92badd;
  transform: rotateZ(90deg);
}

.scroll-btn small span {
  float: left;
  animation: colors 1.5s infinite;
}

.scroll-btn small span:nth-child(1) {
  animation-delay: 0s;
}

.scroll-btn small span:nth-child(2) {
  animation-delay: 0.33s;
}

.scroll-btn small span:nth-child(3) {
  animation-delay: 0.66s;
}

@keyframes colors {
  0%,
  40%,
  100% {
    opacity: 0;
  }
  75% {
    opacity: 1;
  }
}

@media (max-width: 576px) {
  .text_content_1 {
    font-size: 40px;
    top: 140px;
  }
}
@media (min-width: 577px) {
  .text_content_1 {
    font-size: 80px;
    top: 240px;
  }
}
</style>
