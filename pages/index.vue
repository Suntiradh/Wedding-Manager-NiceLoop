<template>
  <div class="main">
    <Navbar />
    <Trial />
    <Promotion />
    <OurService />
    <OurPlatform />
    <HowToUse />
    <Testimonial />
    <Pricing />
    <FAQ />
    <GetStart />
    <ContactUs />
    <Footer />
  </div>
</template>
<script>
export default {
  head() {
    return {
      title: "Wedding Management",
      meta: [
        {
          hid: "description",
          name:  "description",
          content: "All of wedding process manager you can find"
        }
      ]
    } 
  }
}
</script>

<style>
@font-face {
  font-family: 'Anuphan Regular';
  src: local('Anuphan'),
    url(../static/font/Anuphan/Anuphan-Regular.otf) format('truetype');
}
@font-face {
  font-family: 'DM Sans Regular';
  src: local('DM Sans'),
    url(../static/font/DM_Sans/DMSans-Regular.ttf) format('truetype');
}
body {
  color: #262626;
}
.main {
  -webkit-tap-highlight-color: transparent;
  font-family: 'Anuphan Regular';
}
.main label {
  @apply leading-8;
}
.main input {
  @apply border border-gray-200 w-full h-11 rounded-lg;
}
.main button,
a.button {
  background-color: #0855cb;
  color: white !important;
  @apply border-none rounded-3xl py-2 px-7;
}
.section-title {
  @apply text-4xl font-semibold;
}
.section-subtitle {
  @apply text-lg leading-relaxed font-normal text-center;
}
.section-content {
  @apply text-base leading-relaxed font-normal;
}
.container-section {
  @apply mx-auto w-4/5;
}
.section-eng {
  font-family: 'DM Sans';
}
.slick-prev:before,
.slick-next:before {
  line-height: 0;
}
.slick-arrow.slick-prev,
.slick-arrow.slick-next {
  background-color: #fff;
  z-index: 99;
  border: 1px solid #f2f2f2;
  box-shadow: 0px 4px rgba(0, 0, 0, 0.05);
  @apply p-6 mt-6;
}
.main .slick-prev:before {
  content: url('../static/image/left-arrow-mobile.png') !important;
  top: 16px;
  left: 19px;
  @apply absolute;
}
.main .slick-next:before {
  content: url('../static/image/right-arrow-mobile.png') !important;
  top: 16px;
  right: 19px;
  @apply absolute;
}
.slick-dots {
  @apply -bottom-8
}
.slick-dots li button:before {
  font-size: 8px;
  color: #a8bee3;
}
.slick-dots li.slick-active button:before {
  color: #0855cb;
  opacity: 1;
}
.text-blue {
  color: #0855cb;
}
.text-pink {
  color: #ff1d6f;
}
.text-grey {
  color: #a6a6a6;
}
button:focus {
  outline: 0;
}

/* Responsive */
@media (max-width: 768px) {
  .container-section {
    width: 90%;
  }
}
</style>
