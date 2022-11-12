<script setup>
import { ref } from "vue";
import Modal from "./Modal.vue";

const showModal = ref(false);

const toggleModal = () => {
  showModal.value = !showModal.value;
};
</script>

<template>
  <div class="container">
    <!-- CARD 1 -->
    <section class="card">
      <div class="card-logo">
        <img src="../assets/img/image1.png" alt="" />
      </div>

      <div class="price">
        <p>Starter</p>
        <h3>Free</h3>
        <p class="light-text">per month</p>
      </div>

      <ul class="features">
        <li class="feature"><span> &#10004; </span>Full courses library</li>
        <li class="feature"><span> &#10004; </span>A new daily meditation</li>
        <li class="feature">
          <span> &#10004; </span>Access to the meditation guru
        </li>
        <li class="feature low-opacity">
          <span> &#10004; </span>Sleep podcasts and exercises
        </li>
        <li class="feature low-opacity">
          <span> &#10004; </span>Mindfulness exercises
        </li>
        <li class="feature low-opacity">
          <span> &#10004; </span>Guided meditations
        </li>
        <li class="feature low-opacity">
          <span> &#10004; </span>Cooking recipes
        </li>
      </ul>

      <div class="cta">
        <button class="btn" @click="toggleModal">Get Started</button>
      </div>
    </section>

    <!-- CARD 2 -->
    <section class="card py-3 bg-alternate dark-border">
      <div class="card-logo">
        <img src="../assets/img/image2.png" alt="" />
      </div>

      <div class="price">
        <p>Pro</p>
        <h3>$49</h3>
        <p>per month</p>
      </div>

      <ul class="features">
        <li class="feature"><span> &#10004; </span>Full courses library</li>
        <li class="feature"><span> &#10004; </span>A new daily meditation</li>
        <li class="feature">
          <span> &#10004; </span>Access to the meditation guru
        </li>
        <li class="feature">
          <span> &#10004; </span>Sleep podcasts and exercises
        </li>
        <li class="feature"><span> &#10004; </span>Mindfulness exercises</li>
        <li class="feature low-opacity">
          <span> &#10004; </span>Guided meditations
        </li>
        <li class="feature low-opacity">
          <span> &#10004; </span>Cooking recipes
        </li>
      </ul>

      <div class="cta">
        <button class="btn bg-dark" @click="toggleModal">Get Started</button>
      </div>
    </section>

    <!-- CARD 3 -->
    <section class="card py-2">
      <div class="card-logo">
        <div class="img-group">
          <img
            src="../assets/img/image3.png"
            alt=""
            style="position: relative; left: 20px"
          />
          <img src="../assets/img/image4.png" alt="" />
          <img
            src="../assets/img/image5.png"
            alt=""
            style="position: relative; right: 20px"
          />
        </div>
      </div>

      <div class="price">
        <p>Teams</p>
        <h3>$99</h3>
        <p class="light-text">per month</p>
      </div>

      <ul class="features">
        <li class="feature"><span> &#10004; </span>Full courses library</li>
        <li class="feature"><span> &#10004; </span>A new daily meditation</li>
        <li class="feature">
          <span> &#10004; </span>Access to the meditation guru
        </li>
        <li class="feature">
          <span> &#10004; </span>Sleep podcasts and exercises
        </li>
        <li class="feature"><span> &#10004; </span>Mindfulness exercises</li>
        <li class="feature"><span> &#10004; </span>Guided meditations</li>
        <li class="feature"><span> &#10004; </span>Cooking recipes</li>
      </ul>

      <div class="cta">
        <button class="btn bg-alternate" @click="toggleModal">
          Get Started
        </button>
      </div>
    </section>
  </div>

  <div v-if="showModal">
    <Modal :showModal="showModal" @toggleModal="toggleModal" />
  </div>
</template>

<style>
.container {
  width: 1045px;
  height: 684px;
  margin: 50px auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
}

.card {
  border-radius: 10px;
  padding: 1rem;
  width: 30%;
  box-shadow: -1px -3px 10px 5px #d8d8d8;
  background-color: #e2f0ff;
  background-image: linear-gradient(62deg, #e2f0ff 0%, #d2d0d6 100%);
}

.card-logo {
  text-align: center;
}

.price {
  margin: 1rem 0;
}

.price h3 {
  margin: 4px 0;
  font-size: 24px;
}

.features {
  margin: 1rem 0;
}

.feature {
  margin: 1rem 0;
  font-size: 0.9rem;
}

.btn {
  width: 100%;
  font-family: inherit;
  font-weight: 500;
  padding: 12px 0;
  border-radius: 8px;
  border: 1px solid #5a45f2;
  outline: none;
  cursor: pointer;
  transition: all 1s ease;
}

.btn:hover {
  transform: translateY(5px);
}

.btn:active {
  transform: scale(0.98);
}

@media (max-width: 985px) {
  .container {
    max-width: 375px;
  }

  .card {
    width: 85%;
    margin: 1rem auto;
  }
}
</style>
