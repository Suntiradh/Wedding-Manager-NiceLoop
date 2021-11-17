<template>
  <div class="promotion">
    <div class="container-section">
      <div class="box-promotion">
        <div class="my-auto">
          <img src="../static/social-icon/discount.png" class="mx-auto h-16" />
        </div>
        <h2 class="my-auto section-eng font-bold text-blue">
          Promotion is now 25% Discount
        </h2>
        <button class="btn">ใช้ส่วนลดนี้</button>
      </div>
    </div>
  </div>
</template>

<style>
.promotion {
  @apply flex w-full h-16;
}
.promotion .container-section {
  background-color: #f4f9fd;
}
.promotion .box-promotion {
  @apply flex w-1/2 justify-between m-auto container h-16;
}
.promotion .box-promotion button {
  color: #0855cb;
  border-color: #0855cb;
  @apply my-auto bg-white font-semibold border-solid border;
}
.btn {
  color: #0855cb !important;
}
/* Responsive */
@media (max-width: 768px) {
  .promotion {
    @apply h-full;
  }
  .promotion .box-promotion {
    @apply block w-4/5 py-4 text-center h-auto;
  }
  .box-promotion .section-eng {
    @apply pb-4;
  }
  .promotion .box-promotion button {
    @apply mb-4;
  }
  .promotion .box-promotion img {
    @apply mx-auto h-16 -mt-12;
  }
}
</style>
