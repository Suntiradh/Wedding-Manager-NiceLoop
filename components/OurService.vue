<template>
  <div id="our-service">
    <div class="container-section">
      <h3 class="section-title text-center">ฟีเจอร์เด่น</h3>
      <br />
      <p class="text-center w-90 mx-auto section-subtitle">
        s simply dummy text of the printing and typesetting industry. Lorem
        Ipsum has been the industry's standard dummy text ever since the 1500s,
        when an unknown printer took a galley of type and scrambled it to make a
      </p>
      <br />
      <div class="slider large-screen">
        <VueSlickCarousel
          :dots="true"
          :arrows="true"
          :slidesToShow="3"
          :pauseOnHover="true"
          :slidesToScroll="3"
          :touchThreshold="5"
        >
          <div v-for="data in serviceData" :key="data.id">
            <div class="card">
              <div class="over-square">
                <div class="square"></div>
                <img class="absolute top-16" :src="data.icon" alt="" />
              </div>
              <h3 class="font-semibold text-lg text-blue">{{ data.topic }}</h3>
              <br />
              <p class="section-content">
                {{ data.content }}
              </p>
            </div>
          </div>
        </VueSlickCarousel>
      </div>
      <div class="slider small-screen">
        <VueSlickCarousel
          :dots="true"
          :arrows="true"
          :slidesToShow="1"
          :pauseOnHover="true"
          :slidesToScroll="1"
          :touchThreshold="5"
        >
          <div v-for="data in serviceData" :key="data.id">
            <div class="card">
            <!-- <div class="rounded-2xl p-7 box-slider"> -->
              <div class="over-square">
                <div class="square"></div>
                <img class="absolute top-16" :src="data.icon" alt="" />
              </div>
              <h3 class="font-semibold text-lg text-blue">{{ data.topic }}</h3>
              <br />
              <p class="section-content">
                {{ data.content }}
              </p>
            </div>
          </div>
        </VueSlickCarousel>
      </div>
    </div>
  </div>
</template>
<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
// optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

export default {
  components: { VueSlickCarousel },
  data() {
    return {
      serviceData: [
        {
          id: 1,
          topic: 'Initial Consolution',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse in vestibulum',
          icon: require('../static/image/edit-icon.png'),
        },
        {
          id: 2,
          topic: 'Wedding Location',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse in vestibulum',
          icon: require('../static/image/wand-icon.png'),
        },
        {
          id: 3,
          topic: 'Wedding Management',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse in vestibulum',
          icon: require('../static/image/users-icon.png'),
        },
        {
          id: 4,
          topic: 'Mock1 Consolution',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse in vestibulum',
          icon: require('../static/image/edit-icon.png'),
        },
        {
          id: 5,
          topic: 'Mock2 Consolution',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse in vestibulum',
          icon: require('../static/image/edit-icon.png'),
        },
      ],
    }
  },
}
</script>
<style>
#our-service {
  @apply pt-16 pb-32;
}
.slider {
  @apply w-full mx-auto;
}
.slider h3 {
  @apply font-bold text-center;
}
#our-service .slider p {
  @apply text-center;
}
.slick-slide {
  @apply mt-12;
}
.over-square {
  @apply flex justify-center pt-8 pb-16; 
}
.card {
  background-color: #f4f9fd;
  @apply border-none rounded-2xl m-6 p-3 h-64;
}
.over-square .square {
  background-color: #0855cb;
  box-shadow: 20px 20px 40px -20px #0855cb;
  @apply w-24 h-24 rounded-3xl transform rotate-45 absolute top-9;
}
#our-service .slick-prev {
  left: -15px;
}
#our-service .slick-next {
  right: -15px;
}
#our-service .slick-prev:before {
  top: 16px;
  left: 19px;
}
#our-service .slick-next:before {
  top: 16px;
  right: 19px;
}

.w-90 {
  width: 90%;
}
.small-screen {
  @apply hidden;
}

/* Responsive */
@media (max-width: 768px) {
  .box-slider {
    @apply mx-6;
  }
  #our-service {
    @apply pb-16;
  }
  .large-screen {
    @apply hidden;
  }
  .small-screen {
    @apply block;
  }
  /*.slick-arrow.slick-prev,
  .slick-arrow.slick-next {
    background-color: #fff;
    z-index: 99;
    border: 1px solid #f2f2f2;
    box-shadow: 0px 4px rgba(0, 0, 0, 0.05);
    @apply p-6 mt-6;
  }*/
  #our-service .slick-prev {
    left: -13px;
  }
  #our-service .slick-next {
    right: -13px;
  }
  .card {
    @apply m-0;
  }
}
</style>
