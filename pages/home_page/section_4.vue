<template>
  <div class="section_4">
    <div class="background_fixed"></div>
    <div class="container">
      <div class="content_section_4">
        <div class="text-center content_center">
          <div>
            <span class="title_content_4">
              <i>Exhaust Trail Racing Team</i>
            </span>
          </div>
          <div class="desc_content_4">
            Produck yang kami jual /kirim Dijamin Original Aileen
          </div>
          <div class="desc_content_4">
            Siap kirim ke seluruh Indonesia, siap COD (Bayar Ditempat) dan
            pastinya chat penjual sebelum memesan untuk bertanya stock apakah
            masih tersedia atau tidak.
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.section_4 {
  position: relative;
  overflow: hidden;
}

.background_fixed {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('../../assets/model/model_4.jpeg');
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  opacity: 0.5;
  transition: background-image 0.3s, border-radius 0.3s, opacity 0.3s;
  z-index: -1;
}

.container {
  position: relative;
  z-index: 1;
}

.content_section_4 {
  min-height: 450px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.content_center {
  display: flex;
  flex-direction: column;
  gap: 15px;
}
.title_content_4 {
  font-weight: 600;
  line-height: 32px;
  font-size: 32px;
  font-family: 'Poppins';
  text-shadow: 5px 5px 10px #fff;
}
.desc_content_4 {
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  font-family: 'Poppins';
  text-shadow: 5px 5px 10px #fff;
}
</style>
