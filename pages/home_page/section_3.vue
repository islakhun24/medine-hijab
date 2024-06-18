<template>
  <div class="section_3" id="description">
    <div class="container">
      <div class="new_product text-center mb-5">
        <div><i>DESCRIPTION</i></div>
      </div>
      <div class="row align-items-center">
        <div class="col-lg-6 col-md-6 col-12 mb-4 content_left">
          <carousel
            :autoplay="true"
            :nav="false"
            :dots="false"
            :loop="true"
            :items="1"
            :slideSpeed="2000"
          >
            <div v-for="item in dataCarousel" :key="item.id" class="p-1">
              <img :src="item.img" class="image_content" alt="image" />
            </div>
          </carousel>
        </div>
        <div class="col-lg-6 col-md-6 col-12 mb-4 content_right">
          <div class="content_description">
            <h2 class="title_content">Deskripsi Produk</h2>
            <ul>
              <li v-for="(item, xxx) in dataListDescription" :key="xxx">
                {{ item.text }}
              </li>
            </ul>
            <h2 class="title_content">Garansi Produk</h2>
            <ul>
              <li>
                Apabila barang yang diterima tidak sesuai/tidak pas dipasang
                dimotor,barang bisa ditukar(selama belum dipakai).
              </li>
            </ul>
            <h2 class="title_content">Garansi Pengiriman</h2>
            <ul>
              <li>
                Kami siap tukar barang apabila terjadi kerusakan saat pengiriman
                (selama belum dipakai).
              </li>
              <li>Garasi jika tidak Original Aileen siap dikembalikan.</li>
            </ul>
            <h2 class="title_content">PLUG and PLAY</h2>
            <ul>
              <li>KLX 150, BFSE /D-TRACKER 150, CRF 150L, WR 155 R</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="row mb-5">
        <div class="col-lg-6 col-md-6 col-12 mb-4">
          <h6 class="title">NB :</h6>
          <ul>
            <li><small>Sertakan jenis motor saat order</small></li>
            <li><small>Cek kembali barang kiriman sebelum dipakai</small></li>
            <li>
              <small>
                Untuk pemesanan knalpot dengan spesifikasi Bore Up silahkan chat
                langsung, agar kenalpot disesuaikan langsung dengan spesifikasi
                motor anda.
              </small>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dataCarousel: [
        {
          id: 0,
          img: require('../../assets/model/model_11.jpeg'),
        },
        {
          id: 2,
          img: require('../../assets/model/model_1.jpeg'),
        },
        {
          id: 3,
          img: require('../../assets/model/model_3.jpeg'),
        },
      ],
      dataListDescription: [
        {
          id: 0,
          text: 'Free/bonus laser',
        },
        {
          id: 1,
          text: 'Bahan STAINLESS STEEL Anti Karat',
        },
        {
          id: 2,
          text: 'Tebal pipa leher 1,2mm',
        },
        {
          id: 3,
          text: 'Gaswool anti bakar',
        },
        {
          id: 4,
          text: 'Spek stnadar racing/Bore up',
        },
        {
          id: 5,
          text: 'Untuk Crf 150 Klx 150 Dtracker 150 Wr 155',
        },
        {
          id: 5,
          text: 'Spek Suara Ngebass Gahar',
        },
      ],
    }
  },
  methods: {
    goToWhatsapp() {
      const phoneNumber = '6285163523959'
      const message = `Hello min, is the exhaust still available?`
      const url = `https://wa.me/${phoneNumber}?text=${message}`
      window.open(url, '_blank')
    },
  },
}
</script>

<style scoped>
.section_3 {
  font-family: 'Poppins';
  min-height: 650px;
  display: flex;
  align-items: center;
}
img {
  width: 100%;
  border-radius: 10px;
}
.title_content {
  font-size: 20px;
  font-weight: 600;
}
.new_product {
  font-size: 40px;
  font-weight: 700;
  text-align: center;
}
.image_content {
  height: 350px;
}
@media (max-width: 768px) {
  .content_left {
    order: 2;
  }
  .content_right {
    order: 1;
  }
}
</style>
