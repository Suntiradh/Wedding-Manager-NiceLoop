<template>
  <div class="footer">
    <div class="container-section flex">
      <div class="logo">
        <h2><a href="/"><img src="../static/logo/logo.png" alt=""></a></h2>
      </div>
      <div class="menu w-1/3">
        <ul>
          <li>
            <nuxt-link :to="{ path: '/',hash:'our-service'}">ฟีเจอร์</nuxt-link>
          </li>
          <li>
            <nuxt-link :to="{ path: '/',hash:'how-to-use'}">วิธีการใช้งาน</nuxt-link>
          </li>
          <li>
            <nuxt-link :to="{ path: '/',hash:'pricing'}">แพ็กเกจ</nuxt-link>
          </li>
          <li>
            <nuxt-link :to="{ path: '/',hash:'faq'}">คำถามที่พบบ่อย</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="contact w-1/3">
        <ul>
          <li>
            <h3>Contact</h3>
          </li>
          <li>
            <p>Tel:(+66)80-800-8000</p>
          </li>
          <li>
            <div class="contact-link">
              <a href="#"
                ><img
                  src="../static/social-icon/discord-bubble-icon.png"
                  alt="discord"
              /></a>
              <a href="#"
                ><img
                  src="../static/social-icon/facebook-icon.png"
                  alt="facebook"
              /></a>
              <a href="#"
                ><img src="../static/social-icon/line-icon.png" alt="line"
              /></a>
              <a href="#"
                ><img
                  src="../static/social-icon/twitter-icon.png"
                  alt="twitter"
              /></a>
            </div>
          </li>
        </ul>
      </div>
    </div>
    <div class="container-section copyright">
      <p class="text-xs"> &copy; Coppyright 2020 All Rights Reserved</p>
    </div>
  </div>
</template>

<style>
.footer {
  background-color: #262626;
  @apply text-white py-12;
}
.contact-link {
  @apply flex justify-between w-1/2;
}
.menu li {
  @apply my-4;
}
.contact li {
  @apply my-4;
}
.contact h3 {
  color: #a6a6a6;
}

/* Responsive */
@media (max-width: 768px) {
  .footer {
    @apply py-10;
  }
  .footer .container-section.flex {
    @apply block;
  }
  .footer .menu {
    @apply mb-12 mt-16;
  }

  .footer .menu,
  .footer .contact {
    @apply w-full;
  }
  .copyright {
    @apply text-center pt-12;
  }
}
</style>
