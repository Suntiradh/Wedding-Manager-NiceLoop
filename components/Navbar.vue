<template>
  <div class="navbar">
    <div class="top-nav container-section">
      <div class="logo">
        <h2>
          <a href="/"><img src="../static/logo/logo.png" alt="" /></a>
        </h2>
      </div>
      <div class="link">
        <nuxt-link :to="{ path: '/' }">หน้าหลัก</nuxt-link>
        <nuxt-link :to="{ path: '/', hash: 'our-service' }">ฟีเจอร์</nuxt-link>
        <nuxt-link :to="{ path: '/', hash: 'how-to-use' }"
          >วิธีการใช้งาน</nuxt-link
        >
        <nuxt-link :to="{ path: '/', hash: 'pricing' }">แพ๊กเกจ</nuxt-link>
        <nuxt-link
          :to="{ path: '/', hash: 'get-start' }"
          class="button"
          >เริ่มต้นใช้งาน</nuxt-link
        >
      </div>
      <div
        @click="showMobileMenu = !showMobileMenu"
        class="sm:flex md:hidden p-2.5"
      >
        <img src="../static/social-icon/hamberger.png" alt="hamberger" />
      </div>
      <div id="nav-mobile" class="bg-white" v-if="showMobileMenu">
        <div>
          <div @click="showMobileMenu = !showMobileMenu">
            <img
              src="../static/social-icon/hamberger.png"
              alt="hamberger"
              class="float-right"
            />
          </div>
        </div>
        <ul @click="showMobileMenu = !showMobileMenu">
          <li><nuxt-link :to="{ path: '/' }">หน้าหลัก</nuxt-link></li>
          <li>
            <nuxt-link :to="{ path: '/', hash: 'our-service' }"
              >ฟีเจอร์</nuxt-link
            >
          </li>
          <li>
            <nuxt-link :to="{ path: '/', hash: 'how-to-use' }"
              >วิธีการใช้งาน</nuxt-link
            >
          </li>
          <li>
            <nuxt-link :to="{ path: '/', hash: 'pricing' }">แพ๊กเกจ</nuxt-link>
          </li>
          <li>
            <nuxt-link :to="{ path: '/', hash: 'get-start' }" class="button"
              >เริ่มต้นใช้งาน</nuxt-link
            >
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      showMobileMenu: false,
      windowHeight: { height: `40px` },
    }
  },
  methods: {},
}
</script>

<style>
.navbar {
  @apply py-4 h-16;
}
.top-nav {
  @apply flex justify-between;
}
.logo {
  @apply w-1/2;
}
.link {
  @apply flex justify-around w-1/2;
}
.link a,
.navbar a {
  @apply cursor-pointer;
}
.link a {
  color: #0855cb;
  @apply px-4 font-semibold text-base py-2 px-4;
}
#nav-mobile {
  height: 99vh;
  z-index: 100;
  @apply right-0 top-0 py-10 pl-10 pr-6  text-right fixed w-4/5;
}
#nav-mobile ul li {
  @apply my-10;
}

/* Responsive */
@media (max-width: 768px) {
  .navbar {
    box-shadow: 0px 4px 0px 0px #0000000d;
  }
  .link {
    @apply hidden;
  }
}
</style>
