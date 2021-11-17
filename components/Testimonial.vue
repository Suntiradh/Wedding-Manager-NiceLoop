<template>
  <div class="testimonail">
    <div class="container-section">
      <div>
        <h1 class="section-title text-center">เสียงจากผู้ใช้จริง</h1>
      </div>
      <br />
      <div class="slider large-screen">
        <VueSlickCarousel :arrows="true" :slidesToShow="2" :dots="true">
          <div v-for="review in reviews" :key="review.id">
            <div class="p-6 rounded-2xl bg-white m-4 h-64">
              <div class="flex">
                <img class="m-4 w-10" :src="review.image" alt="profile" />
                <ul class="my-auto">
                  <li>
                    <p class="text-xl review-name">{{ review.name }}</p>
                  </li>
                  <li>
                    <p class="review-date">{{ review.date }}</p>
                  </li>
                </ul>
              </div>
              <div>
                <p class="section-content">
                  {{ review.content }}
                </p>
              </div>
            </div>
          </div>
        </VueSlickCarousel>
      </div>
      <div class="slider small-screen">
        <VueSlickCarousel :dots="true" :arrows="true" :slidesToShow="1">
          <div v-for="review in reviews" :key="review.id">
            <div class="p-6 rounded-2xl bg-white m-4 h-64">
              <div class="profile-image">
                <img :src="review.image" alt="profile" />
                <ul class="my-auto ml-5">
                  <li>
                    <p class="text-xl review-name">{{ review.name }}</p>
                  </li>
                  <li>
                    <p class="review-date">{{ review.date }}</p>
                  </li>
                </ul>
              </div>
              <br />
              <div>
                <p class="section-content">
                  {{ review.content }}
                </p>
              </div>
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
import Icon from '../static/image/user-icon.png'
// optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

export default {
  name: 'Testimonail',
  components: { VueSlickCarousel },
  data() {
    return {
      reviews: [
        {
          id: 1,
          image: Icon,
          name: 'Golffy & Honney',
          date: '02/11/2021',
          content:
            'simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a',
        },
        {
          id: 2,
          image: Icon,
          name: 'Golffy & Honney2',
          date: '02/08/2021',
          content:
            'simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a',
        },
        {
          id: 3,
          image: Icon,
          name: 'Golffy & Honney3',
          date: '02/09/2021',
          content:
            'simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a',
        },
        {
          id: 4,
          image: Icon,
          name: 'Golffy & Honney4',
          date: '02/10/2021',
          content:
            'simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a',
        },
        {
          id: 5,
          image: Icon,
          name: 'Golffy & Honney5',
          date: '02/12/2021',
          content:
            'simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a',
        },
      ],
    }
  },
}
</script>

<style>
.testimonail {
  background-color: #ecf1f9;
  @apply py-20;
}
.review-date {
  color: #a6a6a6;
  font-size: 14px;
}
.profile-image {
  @apply flex;
}
.profile-image img {
  @apply m-4 w-10;
}
.testimonail .slick-prev {
  left: -43px;
}
.testimonail .slick-next {
  right: -43px;
}

.small-screen {
  @apply hidden;
}

/* Responsive */
@media (max-width: 768px) {
  .testimonail {
    @apply py-16;
  }
  .testimonail .slick-track .bg-white {
    @apply p-11;
  }
  .profile-image img {
    @apply m-4 w-12;
  }
  .large-screen {
    @apply hidden;
  }
  .small-screen {
    @apply block;
  }
  .testimonail .slick-arrow.slick-prev,
  .testimonail .slick-arrow.slick-next {
    @apply p-6 mt-0 z-50 bg-white;
  }
  .testimonail .slick-prev {
    left: -13px;
  }
  .testimonail .slick-next {
    right: -13px;
  }
  .testimonail .slick-slide .h-64 {
    @apply h-full;
  }
  .testimonail .slick-slide .m-4 {
    @apply m-0;
  }
  .testimonail .slick-slide {
    @apply mt-0;
  }
}
</style>
