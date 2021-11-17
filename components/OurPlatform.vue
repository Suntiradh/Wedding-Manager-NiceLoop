<template>
  <div class="our-platform">
    <div class="container-section flex">
      <div class="text-our-platform">
        <h1 class="section-title -mx-px text-white">รู้จักแพลตฟอร์มของเรา</h1>
        <br />
        <p class="text-white">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptas
          consequuntur, accusantium ad nam modi alias libero iste ea facilis
          facere! Rem suscipit temporibus quod eum accusantium, quibusdam
          inventore corrupti non?
        </p>
        <br />
      </div>
      <div class="w-1/2 ml-4 img-our-platform">
        <img class="mx-auto" src="../static/image/our-platform.png" alt="" />
      </div>
    </div>
  </div>
</template>
<style>
.our-platform {
  background-image: linear-gradient(to left, #074cb5, #0a67f5);
  @apply pt-20;
}
.our-platform button {
  @apply border border-solid border-gray-500;
}
.img-our-platform {
  margin-bottom: -1px;
}
.text-our-platform {
  @apply w-1/2 my-auto pb-16;
}
@media (max-width: 768px) {
  .our-platform {
    @apply py-16;
  }
  .our-platform .flex {
    @apply block;
  }
  .text-our-platform,
  .img-our-platform {
    @apply w-full;
  }
  .text-our-platform {
    @apply mt-0;
  }
  .img-our-platform {
    @apply mx-auto py-4;
  }

}
</style>
