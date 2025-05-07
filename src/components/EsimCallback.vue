<template>
  <transition name="modal-fade">
    <div v-if="show" class="modal-overlay" @click.self="close">
      <div class="modal">
        <button class="modal__close" @click="close">&times;</button>

        <h2 class="modal__title">Contact support</h2>
        <p class="modal__subtitle" v-if="!success">Get in touch with our support team if you need help.</p>

        <form v-if="!success" @submit.prevent="submit" class="modal__form">
          <input
              type="email"
              v-model="email"
              placeholder="Email"
              class="modal__input"
              required
          />
          <textarea
              v-model="message"
              placeholder="Your message"
              class="modal__textarea"
              required
          ></textarea>
          <EsimButton type="submit" class="modal__send">Send</EsimButton>
          <p class="modal__policy">
            By clicking 'Send' I agree with <a href="#">Privacy Policy</a>
          </p>
        </form>

        <div v-else class="modal__success">
          <div class="modal__check">
            <img src="@/assets/images/check.svg" alt="">
          </div>
          <p>Your message has been sent</p>
          <EsimButton type="submit" color="outline" class="modal__close-btn" @click="close">Close</EsimButton>
        </div>
      </div>
    </div>
  </transition>
  <button @click="show = true" class="callback-btn">
    <img src="@/assets/images/message.svg" alt="">
  </button>
</template>

<script setup>
import { ref } from 'vue';
import EsimButton from "@/components/EsimButton.vue";


const show = ref(false);
const email = ref('');
const message = ref('');
const success = ref(false);

function close() {
  show.value = false;
  setTimeout(() => {
    email.value = '';
    message.value = '';
    success.value = false;
  }, 300);
}

function submit() {
  setTimeout(() => {
    success.value = true;
  }, 500);
}
</script>

<style scoped lang="scss">
.modal-overlay {
  position: fixed;
  inset: 0;
  background-color: rgba(0, 0, 0, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal {
  position: relative;
  width: 500px;
  background: #1b1729;
  border-radius: 16px;
  padding: 0 32px 32px;
  color: #fff;
  font-family: sans-serif;
  box-shadow: 0 0 40px rgba(0, 0, 0, 0.4);

  &__close {
    position: absolute;
    top: 32px;
    right: 32px;
    background: none;
    border: none;
    color: #999;
    font-size: 24px;
    cursor: pointer;
  }

  &__title {
    font-size: 36px;
    font-weight: bold;
    padding: 24px 0;
    margin-bottom: 24px;
  }

  &__subtitle {
    font-size: 16px;
    color: #7f8a9f;
    margin-bottom: 16px;
  }

  &__form {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  &__input{
    height: 56px;
  }
  &__input,
  &__textarea {
    background: #2b2a3d;
    border: none;
    border-radius: 8px;
    padding: 12px;
    color: #fff;
    font-size: 14px;
    resize: none;

    &::placeholder {
      color: #aaa;
    }
  }

  &__textarea {
    height: 144px;
  }

  &__send {
    border: none;
    font-weight: bold;
  }

  &__policy {
    font-size: 12px;text-align: center;
    color: #888;
    a {
      color: #888;
      text-decoration: underline;
    }
  }

  &__success {
    text-align: center;
    margin: 20px 0;
    p {
      margin-top: 12px;
      font-size: 14px;
      color: #7f8a9f;
    }
  }

  &__check {
    width: 64px;
    margin: 0 auto;
    background: linear-gradient(to right, #6d4eff, #a661ff);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;

    svg {
      width: 28px;
      height: 28px;
    }
  }

  &__close-btn {
    width: 100%;
    margin-top: 20px;
  }
}

.callback-btn {
  background: none;
  border: none;
  outline: none;
  position: fixed;
  right: 24px;
  bottom: 24px;
}

.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.3s ease;
}
.modal-fade-enter-from,
.modal-fade-leave-to {
  opacity: 0;
}
</style>
