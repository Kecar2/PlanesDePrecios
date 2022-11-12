<script setup>
import { ref } from "vue";

const props = defineProps(["showModal"]);

const email = ref("");
const errorMsg = ref("");
const formSubmitted = ref(false);

const validateForm = () => {
  // Email Validation
  let emailPattern = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,5}))$/;
  let emailValidation = emailPattern.test(email.value);
  if (!emailValidation) {
    errorMsg.value = "Invalid email address.";
  } else {
    formSubmitted.value = true;
    errorMsg.value = "";
  }
};
</script>

<template>
  <div class="modal-wrapper" @click.self="$emit('toggleModal')">
    <div class="modal" v-if="!formSubmitted">
      <div class="modal-header">
        <h2>Contact us</h2>
      </div>

      <form class="form" @submit.prevent="validateForm">
        <input type="email" name="email" placeholder="Your email address.." v-model="email" />
        <p class="error">{{ errorMsg }}</p>
        <button class="modal-btn">Submit</button>
      </form>
    </div>

    <div class="modal py-3" v-else>
      <h2>Thanks, we will contact you soon!</h2>
    </div>
  </div>
</template>

<style>
.modal-wrapper {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(4px);
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  width: 400px;
  text-align: center;
  border-radius: 8px;
  background: #5a45f2;
  color: white;
  padding: 1rem;
  position: relative;
}

.modal-header {
  margin: 10px 0;
}

input[type="email"] {
  padding: 8px 10px;
  margin: 10px 0;
  border-radius: 30px;
  border: none;
  outline: none;
  color: #5a45f2;
}

.error {
  color: orangered;
  font-weight: 500;
}

.modal-btn {
  display: block;
  margin: 10px auto;
  width: 30%;
  color: #5a45f2;
  font-family: inherit;
  font-weight: 500;
  padding: 8px 10px;
  border-radius: 8px;
  border: none;
  outline: none;
  cursor: pointer;
  transition: all 1s ease;
}
</style>
