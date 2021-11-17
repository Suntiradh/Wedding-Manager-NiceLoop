<template>
  <div id="faq">
    <div class="container-section">
      <h3 class="section-title mb-2.5">คำถามที่พบบ่อย</h3>
      <p class="leading-loose">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto
        illo aliquid ducimus blanditiis fugit sit exercitationem deleniti.
      </p>
      <br />
      <div class="flex section-faq">
        <div class="w-1/2 mr-4">
          <ShowAnswer
            v-for="question in questions.slice(0, 4)"
            :key="question.id"
            :data="question"
          />
        </div>
        <div class="w-1/2 ml-4">
          <ShowAnswer
            v-for="question in questions.slice(4, 8)"
            :key="question.id"
            :data="question"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ShowAnswer from './ShowAnswer.vue'
export default {
  name: 'FAQ',
  components: {
    ShowAnswer,
  },
  data() {
    return {
      questions: [
        {
          id: 1,
          question: 'The most popular question',
          answer:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos numquam possimus asperiores, voluptatum esse doloribus doloremque nesciunt aspernatur, sed cum laborum sapiente nulla libero! Iure deleniti itaque at nihil ipsum.',
        },
        {
          id: 2,
          question: 'The most popular question',
          answer:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos numquam possimus asperiores, voluptatum esse doloribus doloremque nesciunt aspernatur, sed cum laborum sapiente nulla libero! Iure deleniti itaque at nihil ipsum.',
        },
        {
          id: 3,
          question: 'The most popular question',
          answer:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos numquam possimus asperiores, voluptatum esse doloribus doloremque nesciunt aspernatur, sed cum laborum sapiente nulla libero! Iure deleniti itaque at nihil ipsum.',
        },
        {
          id: 4,
          question: 'The most popular question',
          answer:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos numquam possimus asperiores, voluptatum esse doloribus doloremque nesciunt aspernatur, sed cum laborum sapiente nulla libero! Iure deleniti itaque at nihil ipsum.',
        },
        {
          id: 5,
          question: 'The most popular question',
          answer:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos numquam possimus asperiores, voluptatum esse doloribus doloremque nesciunt aspernatur, sed cum laborum sapiente nulla libero! Iure deleniti itaque at nihil ipsum.',
        },
        {
          id: 6,
          question: 'The most popular question',
          answer:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos numquam possimus asperiores, voluptatum esse doloribus doloremque nesciunt aspernatur, sed cum laborum sapiente nulla libero! Iure deleniti itaque at nihil ipsum.',
        },
        {
          id: 7,
          question: 'The most popular question',
          answer:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos numquam possimus asperiores, voluptatum esse doloribus doloremque nesciunt aspernatur, sed cum laborum sapiente nulla libero! Iure deleniti itaque at nihil ipsum.',
        },
        {
          id: 8,
          question: 'The most popular question',
          answer:
            'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos numquam possimus asperiores, voluptatum esse doloribus doloremque nesciunt aspernatur, sed cum laborum sapiente nulla libero! Iure deleniti itaque at nihil ipsum.',
        },
      ],
    }
  },
}
</script>
<style>
#faq {
  background-color: #ecf1f9;
  @apply py-12;
}

.show-answer {
  @apply py-4 border-white;
}
.border-b-2 {
  border-bottom-width: 2px;
}
.show-answer .flex {
  @apply px-4;
}
.section-faq img {
  @apply cursor-pointer;
}
/* Responsive */
@media (max-width: 768px) {
  #faq .section-title {
    @apply text-left;
  }
  #faq .section-faq {
    @apply block;
  }
  #faq .section-faq .w-1\/2 {
    @apply w-full;
  }
  #faq .section-faq .ml-4 {
    @apply ml-0;
  }
  #faq h3.section-title {
    @apply mb-10;
  }
}
</style>
