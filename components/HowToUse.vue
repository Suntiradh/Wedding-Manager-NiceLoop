<template>
  <div id="how-to-use">
    <div class="container-section flex justify-between">
      <div class="width-45 tab-1">
        <h3 class="section-title">วิธีการใช้งาน</h3>
        <br />
        <p class="text-lg font-normal leading-relaxed">
          s simply dummy text of the printing and typesetting industry. Lorem
          Ipsum has been the industry's
        </p>
        <div class="img-section">
          <div class="macbook-img" v-if="isShow">
            <img src="../static/image/how-to-desktop.png" alt="" class="mt-8" />
          </div>
          <div class="iphone-img" v-else-if="!isShow">
            <img
              src="../static/image/how-to-mobile.png"
              alt=""
              class="mx-auto"
            />
          </div>
        </div>
      </div>
      <div class="width-45 tab-2">
        <br />
        <div class="switch">
          <div
            class="my-auto text-white"
            @click="isShow = true"
            :class="{ active: isShow === true }"
          >
            สำหรับบ่าวสาว
          </div>
          <div
            class="my-auto text-white"
            @click="isShow = false"
            :class="{ active: isShow === false }"
          >
            สำหรับแขก
          </div>
        </div>
        <br />
        <div
          class="flex my-8"
          v-for="manual in isShow ? coupleManuals : guestManuals"
          :key="manual.id"
        >
          <div class="m-auto mr-7">
            <div class="circle">
              <span class="text-center py-1.5 text-2xl number">{{
                manual.id
              }}</span>
            </div>
          </div>
          <div class="content-for-to-use">
            <h3 class="font-bold text-lg mb-4 text-blue">{{ manual.title }}</h3>
            <p class="section-content">
              {{ manual.content }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'HowToUse',
  data() {
    return {
      isShow: true,
      coupleManuals: [
        {
          id: '01',
          title: 'สร้างฟอร์มลงทะเบียน',
          content:
            's simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry ',
        },
        {
          id: '02',
          title: 'ปรับแต่งการ์ดงานแต่ง',
          content:
            's simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry ',
        },
        {
          id: '03',
          title: 'ส่งการ์ดเชิญเข้า LINE',
          content:
            's simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry ',
        },
        {
          id: '04',
          title: 'ดูข้อมูลสรุปแขกร่วมงาน',
          content:
            's simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry ',
        },
      ],
      guestManuals: [
        {
          id: '01',
          title: 'ดูการ์ดเชิญทางแชท LINE',
          content:
            's simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry ',
        },
        {
          id: '02',
          title: 'ลงทะเบียนเข้าร่วมงาน',
          content:
            's simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry ',
        },
        {
          id: '03',
          title: 'ลงทะเบียนเข้าร่วมงาน',
          content:
            's simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry ',
        },
      ],
    }
  },
}
</script>

<style>
#how-to-use {
  height: 720px;
  @apply py-20;
}
.width-45 {
  width: 45%;
}
#how-to-use .content-for-to-use p {
  @apply leading-normal;
}
.circle {
  height: 55px;
  width: 55px;
  position: relative;
  background-color: rgb(255 29 111 / 10%);
  border-radius: 50%;
}
.switch {
  background-color: #0855cb;
  @apply rounded-full w-72 flex justify-between p-2;
}
.circle span {
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%);
  color: #ff1d6f;
}
.rounded-full .my-auto,
.rounded-full .my-auto.active {
  @apply px-6 py-2;
}
.my-auto.active {
  color: #0855cb;
  @apply bg-white rounded-3xl;
}
.img-section {
  @apply h-44;
}
.iphone-img {
  @apply mt-4;
}

@media (max-width: 768px) {
  #how-to-use {
    @apply py-12 h-auto;
  }
  #how-to-use .container-section.flex {
    @apply block;
  }
  .width-45 {
    @apply w-full;
  }
  .section-title {
    @apply text-center;
  }
  .tab-2 {
    @apply mt-4;
  }
  .m-auto {
    @apply mt-0;
  }
  .circle span.number {
    @apply text-lg;
  }
  .macbook-img {
    /* padding: 60px 0px 0px 0px; */
    @apply mt-12;
  }
  .img-section {
    @apply h-60;
  }
  .macbook-img img {
    @apply h-56 m-auto;
  }
  .iphone-img {
    @apply mt-12;
  }
  .iphone-img img {
    @apply h-56;
  }
}
</style>
