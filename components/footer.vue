<template>
  <footer class="footer bg-dark text-white">
    <div class="text-center">
      <small class="mb-0 fw-bold">
        Copyright © {{ new Date().getFullYear() }} Medine - Hijab Store
      </small>
    </div>
  </footer>
</template>

<script>
export default {}
</script>

<style scoped>
.footer {
  box-shadow: 0 0 10px #464647;
  min-height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.text_left {
  text-align: left;
}
</style>
