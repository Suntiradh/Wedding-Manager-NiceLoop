<template>
  <div class="contact-us">
    <div class="container-section">
      <div class="content">
        <h2 class="text-xl">สอบถามข้อมูลเพิ่มเติม</h2>
        <br />
        <p class="text-grey">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci a
          repellendus quod veniam quisquam maiores harum.
        </p>
        <br />
        <div class="input">
          <form ref="form" @submit.prevent="sendEmail">
            <div class="form-input">
              <div class="w-1/2 mr-4">
                <div>
                  <label for="name">ชื่อ-นามสกุล</label>
                  <br />
                  <input v-model="name" type="text" name="name" />
                </div>
                <br />
                <div>
                  <label for="email">อีเมล</label>
                  <br />
                  <input v-model="email" type="email" name="email" />
                </div>
                <br />
                <div>
                  <label for="tel">เบอร์ติดต่อ</label>
                  <br />
                  <input v-model="telephone" type="text" name="telephone" />
                </div>
              </div>
              <div class="message">
                <label for="message">ข้อความ</label>
                <br />
                <textarea
                  class="h-60 w-full resize-none rounded-lg"
                  v-model="message"
                  name="message"
                ></textarea>
                <br />
              </div>
            </div>
            <div class="flex justify-end w-full mt-6 button-submit">
              <button class="w-40" type="submit">ส่งคำถาม</button>
            </div>
            <div v-if="warning" class="text-red-400">
              * กรุณาใส่ข้อมูลให้ครบถ้วน
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import emailjs from 'emailjs-com'
import swal from 'sweetalert2'
export default {
  name: 'ContactUs',
  data() {
    return {
      name: '',
      email: '',
      telephone: '',
      message: '',
      warning: false,
    }
  },
  methods: {
    verifyInfo() {
      if (
        this.name === '' ||
        this.email === '' ||
        this.telephone === '' ||
        this.message === ''
      ) {
        this.warning = true
        return false
      } else {
        return true
      }
    },
    async sendEmail() {
      if (this.verifyInfo() === false) return
      // const serviceID = 'service_30va2lp'
      // const templateID = 'template_7lzb2d9'
      // const userID = 'user_KuyTAQ9AtoZvzXZbtRjPt'
      try {
        // await emailjs.sendForm(serviceID, templateID, this.$refs.form, userID, {
        //   name: this.name,
        //   email: this.email,
        //   message: this.message,
        //   telephone: this.telephone,
        // })
        await new swal({
          title: `Success!`,
          icon: 'success',
          buttonsStyling: true,
          confirmButtonClass: 'btn btn-success btn-fill',
        })
        this.warning = false
      } catch (error) {
        console.log({ error })
      }
      this.name = ''
      this.email = ''
      this.telephone = ''
      this.message = ''
    },
  },
}
</script>

<style>
.contact-us {
  @apply py-16;
}
.content {
  width: 70%;
  background-color: #ecf1f9;
  @apply mx-auto p-14 rounded-3xl;
}
.form-input {
  @apply flex;
}
.message {
  @apply w-1/2 ml-4;
}
/* Responsive */
@media (max-width: 768px) {
  .contact-us {
    @apply bg-gray-100 py-8 mt-12 mb-8;
  }
  .contact-us .content {
    @apply w-full rounded-none p-0;
  }
  .contact-us .content p,
  .contact-us .content h2 {
    @apply text-center;
  }
  .form-input {
    @apply block;
  }
  .message {
    @apply w-1/2 ml-0;
  }
  .input .w-1\/2,
  .main .contact-us input,
  .contact-us textarea {
    @apply w-full;
  }
  .input,
  .input .grid {
    @apply block;
  }
  .button-submit {
    @apply justify-center;
  }
}
</style>
