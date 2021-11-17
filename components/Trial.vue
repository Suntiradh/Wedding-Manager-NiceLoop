<template>
  <div class="trial">
    <div class="container-section flex h-full">
      <div class="heading-content">
        <h1 class="text-5xl font-semibold">จัดการงานแต่งง่ายๆ แค่ปลายนิ้ว</h1>
        <h5 class="leading-7 font-semibold pt-6 py-8 text-xl">
          แพลตฟอร์มสำหรับเจ้าบ่าวและเจ้าสาวกับระบบลงทะเบียนที่จะช่วยให้คุณจัดการงานมงคลสมรสของคุณได้ง่ายกว่า
        </h5>

        <!--<div class="button-start">
          <button class="w-40 font-semibold">เริ่มต้นใช้งาน</button>
        </div>-->
      </div>
      <div class="my-auto">
        <img src="../static/image/banner.png" alt="banner" />
      </div>
    </div>
  </div>
</template>
<script>
export default {}
</script>

<style>
.trial {
  @apply py-10;
}
.trial h1 {
  line-height: 56px;
  background: linear-gradient(
    180deg,
    rgba(6, 62, 147, 1) 17%,
    rgba(10, 103, 245, 1) 53%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.heading-content {
  @apply my-auto w-3/6 pr-12; 
}

/* Responsive */
@media (max-width: 768px) {
  .trial .flex {
    @apply block;
  }
  .button-start {
    @apply text-center;
  }
  .trial .w-3\/6 {
    @apply w-full mb-8;
  }
   .trial .heading-content {
  @apply my-auto w-full pr-0 text-center; 
}
}
</style>
