<template>
  <div class="show-answer border-b-2 border-gray-300">
    <div class="flex justify-between">
      <h3>{{ data.question }}</h3>
      <img
        @click="showAnswer = !showAnswer"
        src="https://img.icons8.com/material-outlined/24/000000/expand-arrow--v1.png"
      />
    </div>
    <transition name="slide">
      <ul class="list" v-if="showAnswer">
        <li>
          <p>{{ data.answer }}</p>
        </li>
      </ul>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'ShowAnswer',
  props: {
    data: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      showAnswer: false,
    }
  },
}
</script>

<style>
.list {
  /* position: absolute; */
  width: 100%;
  margin: 0;
  padding: 0;
  list-style-type: none;
  transform-origin: top;
  transition: transform .3s ease-in-out;
  overflow: hidden;
}
.list li {
  padding: 10px;
  border-bottom: solid thin #eee;
  border-left: solid medium #cbc;
}
.slide-enter,
.slide-leave-to {
  transform: scaleY(0);
}
</style>
