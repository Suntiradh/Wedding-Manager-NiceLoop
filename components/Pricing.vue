<template>
  <div id="pricing">
    <div class="container-section">
      <h1 class="mobile section-title text-center">เลือกแพ็กเกจที่ตอบโจทย์</h1>
      <br />
      <p class="w-4/5 mx-auto section-subtitle">
        s simply dummy text of the printing and typesetting industry. Lorem
        Ipsum has been the industry's
      </p>
      <br />
      <br />
      <div class="pricing-option">
        <div v-for="data in packages" :key="data.id" class="pricing-modal">
          <h5 class="text-blue">{{ data.title }}</h5>
          <p>{{ data.subtitle }}</p>
          <br />
          <h3 class="text-pink">{{ data.price }}</h3>
          <br />
          <div class="w-14 h-1 hr-unerline-text"></div>
          <br />
          <div
            class="flex my-2"
            v-for="(info, index) in data.description"
            :key="index"
          >
            <div class="w-1/5 my-auto">
              <img src="../static/social-icon/check-circle.png" alt="" />
            </div>
            <div class="text-gray-200">
              <p class="section-content">
                {{ info.detail }}
              </p>
            </div>
          </div>
          <br />
          <div v-if="data.buttonTag === 'ลองใช้ฟรี'">
            <button class="w-full">{{ data.buttonTag }}</button>
          </div>
          <div v-else>
            <button @click="showModal" class="w-full">{{ data.buttonTag }}</button>
          </div>
        </div>
      </div>
      <transition name="modal-fade">
        <div v-if="isModalVisible" class="modal-backdrop">
          <div class="modal">
            <div class="p-6">
              <header class="modal-header">
                <slot name="header"
                  ><h5>Premium Plan</h5></slot
                >
                <button type="button" class="btn-close" @click="closeModal">
                  x
                </button>
              </header>

              <section class="modal-body">
                <slot name="body"
                  >s simply dummy text of the printing and typesetting industry.
                  Lorem Ipsum has been the industry's
                </slot>
              </section>

              <footer class="modal-footer">
                <slot name="footer">
                  <form class="w-full" ref="form" @submit.prevent="sendEmail">
                    <div class="form-input flex">
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
                      </div>
                      <div class="message w-1/2 ml-4">
                        <div>
                          <label for="tel">เบอร์ติดต่อ</label>
                          <br />
                          <input
                            v-model="telephone"
                            type="text"
                            name="telephone"
                          />
                        </div>
                      </div>
                    </div>
                    <div class="flex justify-end w-full">
                      <button class="w-40" type="submit">ส่งข้อมูล</button>
                    </div>
                    <div v-if="warning" class="text-red-400">
                      <p>* กรุณาใส่ข้อมูลให้ครบถ้วน</p>
                    </div>
                  </form>
                </slot>
              </footer>
            </div>
          </div>
        </div>
      </transition>
    </div>
  </div>
</template>
<script>
import emailjs from 'emailjs-com'
import swal from 'sweetalert2'

export default {
  name: 'Pricing',
  data() {
    return {
      bahtIcon: '&#3647',
      isModalVisible: false,
      name: '',
      email: '',
      telephone: '',
      warning: false,
      packages: [
        {
          id: 1,
          title: 'Basic',
          subtitle: 'Essensials Feature',
          price: 'Free',
          buttonTag: 'ลองใช้ฟรี',
          description: [
            {
              detail: 'simply dummy text of the printing and typesetting',
            },
            {
              detail: 'simply dummy text of the printing and typesetting',
            },
            {
              detail: 'simply dummy text of the printing and typesetting',
            },
          ],
        },
        {
          id: 2,
          title: 'Premium',
          subtitle: 'Essentials Feature + Delivery',
          price: '1500฿',
          buttonTag: 'เลือกแพลนนี้',
          description: [
            {
              detail: 'simply dummy text of the printing and typesetting',
            },
            {
              detail: 'simply dummy text of the printing and typesetting',
            },
            {
              detail: 'simply dummy text of the printing and typesetting',
            },
          ],
        },
      ],
    }
  },
  methods: {
    showModal() {
      this.isModalVisible = true
    },
    closeModal() {
      this.isModalVisible = false
    },
    verifyInfo() {
      if (this.name === '' || this.email === '' || this.telephone === '') {
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
        //   telephone: this.telephone,
        // })
        await new swal({
          title: `Success!`,
          buttonsStyling: true,
          icon: 'success',
          confirmButtonClass: 'btn btn-success btn-fill',
        })
        this.isModalVisible = false
      } catch (error) {
        console.log({ error })
      }
      this.name = ''
      this.email = ''
      this.telephone = ''
    },
  },
}
</script>

<style>
#pricing {
  @apply py-12;
}
.pricing-option {
  @apply flex justify-evenly;
}
.pricing-modal {
  background-color: #F4F9FD;
  @apply rounded-3xl p-6 w-80;
}
.pricing-modal h3 {
  @apply font-bold text-4xl;
}
.pricing-modal h5 {
  @apply font-bold text-xl;
}
.pricing-modal p {
  color: #A6A6A6;
  @apply font-normal text-base;
}
/*.pricing-modal button {
  @apply bg-black text-white w-full !important;
}*/
/* .form-input {
  @apply grid grid-cols-2 gap-2;
} */
.hr-unerline-text {
  background-color: #0855CB;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  background: #ffffff;
  box-shadow: 2px 2px 20px 1px;
  display: flex;
  flex-direction: column;
  width: 50%;
  height: 480px;
  border-radius: 1rem;
}
.modal-header h5 {
  @apply font-bold text-xl
}

.modal-fade-enter,
.modal-fade-leave-to {
  opacity: 0;
}
.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.5s ease;
}
.modal-header,
.modal-footer {
  padding: 15px;
  display: flex;
}
.modal-header {
  position: relative;
  color: black;
  justify-content: space-between;
}
.modal-footer {
  flex-direction: column;
  justify-content: flex-end;
}
.modal-body {
  position: relative;
  padding: 20px 10px;
}
.btn-close {
  position: absolute;
  top: 0;
  right: 0;
  border: none;
  font-size: 20px;
  padding: 10px;
  cursor: pointer;
  font-weight: bold;
  color: #0855CB !important;
  background-color: transparent !important;
}
.btn-green {
  color: black;
  background: #4aae9b;
  border: 1px solid #4aae9b;
  border-radius: 2px;
  width: 30%;
}

/* Responsive */
@media (max-width: 768px) {
  .pricing-option {
    @apply block;
  }
  .pricing-modal,
  #pricing .section-subtitle {
    @apply w-full;
  }
  .pricing-option .pricing-modal:first-child {
    @apply mb-6;
  }
  #pricing .section-title {
    @apply leading-normal;
  }
  .mobile {
    @apply w-2/3 m-auto;
  }
  .modal {
    background: #ffffff;
    box-shadow: 2px 2px 20px 1px;
    display: flex;
    flex-direction: column;
    border-radius: 2rem;
    @apply w-11/12 h-auto;
  }
  .form-input {
    @apply block;
  }
  .modal-backdrop .form-input .w-1\/2,
  .main .modal-backdrop input {
    @apply w-full;
  }
  .modal-backdrop .modal .p-6 {
    @apply p-4;
  }
  .modal-backdrop .modal-footer button {
    @apply mt-8;
  }
}
</style>
