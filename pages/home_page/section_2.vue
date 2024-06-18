<template>
  <div class="section_2" id="product">
    <div class="container">
      <div class="content_section_2 text-center mb-5">
        <div><i>HIJAB PRODUCT</i></div>
      </div>
      <div class="content_carousel">
        <carousel
          :autoplay="true"
          :nav="false"
          :dots="true"
          :loop="true"
          :items="1"
          :responsive="responsiveOptions"
          :slideSpeed="2000"
        >
          <div v-for="item in dataCarousel" :key="item.id" class="p-1">
            <div class="card">
              <img :src="item.img" class="card-img-top" alt="image" />
              <div class="card-body">
                <p class="card-title" style="font-weight: 600">
                  {{ item.title }}
                </p>
                <a
                  class="btn btn-primary w-100"
                  @click="goToWhatsapp(item.title)"
                  >Pesan Sekarang</a
                >
              </div>
            </div>
          </div>
        </carousel>
      </div>
      <div class="description_content">
        <div>
          <h6 class="text-center">Tersedia untuk mesin BORE UP Kompetisi</h6>
          <ul>
            <li>Piston 62 disarankan pakai Standard diameter standard 28</li>
            <li>
              Piston 63 keatas disarankan memakai BORE UP dengan diameter BORE
              UP 32.33
            </li>
            <li>
              Piston 68/70 keatas /200cc memakai COMPETITION dengan diameter
              COMPETITION 33/34
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VOwlCarousel from 'v-owl-carousel'
export default {
  components: { VOwlCarousel },
  data() {
    return {
      dataCarousel: [
        {
          id: 1,
          title: 'Series 1.1',
          img: require('../../assets/model/model_2.jpeg'),
        },
        {
          id: 2,
          title: 'Series 1.2',
          img: require('../../assets/model/model_5.jpeg'),
        },
        {
          id: 3,
          title: 'Series 1.3',
          img: require('../../assets/model/model_6.jpeg'),
        },
        {
          id: 4,
          title: 'Series 1.4',
          img: require('../../assets/model/model_7.jpeg'),
        },
        {
          id: 5,
          title: 'Series 1.5',
          img: require('../../assets/model/model_8.jpeg'),
        },
        {
          id: 6,
          title: 'Series 1.6',
          img: require('../../assets/model/model_9.jpeg'),
        },
        {
          id: 7,
          title: 'Series 1.7',
          img: require('../../assets/model/model_10.jpeg'),
        },
      ],
      responsiveOptions: {
        0: {
          items: 1,
        },
        600: {
          items: 2,
        },
        1000: {
          items: 3,
        },
      },
    }
  },
  methods: {
    goToWhatsapp(val) {
      const phoneNumber = '6285163523959'
      const message = `Hello min, is the exhaust with *${val}* still available?`
      const url = `https://wa.me/${phoneNumber}?text=${message}`
      window.open(url, '_blank')
    },
  },
}
</script>

<style scoped>
.section_2 {
  margin: 30px auto;
  min-height: 650px;
}
.content_section_2 {
  font-size: 40px;
  font-weight: 700;
}
.card-img-top {
  width: 100%;
  height: 300px;
  object-fit: cover;
}
.content_section_2,
.description_content,
.card-title,
.card-text {
  font-family: 'Poppins';
}
.description_content h6 {
  font-size: 20px;
  font-weight: 600;
}
.description_content {
  min-height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
