<template>
  <div id="get-start">
    <div class="container-section">
      <h1 class="section-title text-center">เริ่มต้นใช้งานเลย</h1>
      <br>
      <p class="w-2/5 mx-auto text-center">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Et placeat
        velit amet, culpa voluptate repellat
      </p>
      <br>
      <div class="flex justify-center">
      <button>เริ่มต้นใช้งาน</button>
      </div>
    </div>
  </div>
</template>
<style>
#get-start {
  @apply pt-12;
}
#get-start button {
  padding: 0.75rem 3rem !important;
}
/* Responsive */
@media (max-width: 768px) {
  #get-start p {
    @apply w-full;
  }
}
</style>
