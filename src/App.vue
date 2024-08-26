<script>
  import {
    RouterLink,
    RouterView
  } from 'vue-router'

  export default {
    data() {
      return {
        currentIndex: 1,
        currentTime: '',
      }
    },
    created() {
      this.updateTime();
      setInterval(this.updateTime, 1000); // Vaqtni har soniyada yangilash
    },
    methods: {
      NextQuestions() {
        if (this.currentIndex <= 3) {
          this.currentIndex++;
        }
      },

      prewQuestions() {
        if (this.currentIndex > 1) {
          this.currentIndex--;
        }
      },

      updateTime() {
        const now = new Date();
        this.currentTime = now.toLocaleTimeString(); // Vaqtni HH:MM:SS formatida olish
      },
    },
  }
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="/">
        <h4>PISA 2022</h4>
      </a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link active text-primary" aria-current="page" href="#"><i class="fa fa-clock-o"
                aria-hidden="true"></i> {{ currentTime }}</a>
          </li>
        </ul>
        <form class="d-flex">
          <button class="btn btn-outline-primary m-1" type="button" @click="toggleCalculator"><i
              class="fa fa-calculator" aria-hidden="true"></i></button>
          <button class="btn btn-outline-primary m-1" type="button" :disabled="currentIndex==1"
            @click="prewQuestions"><i class="fa fa-arrow-left" aria-hidden="true"></i></button>
          <button class="btn btn-outline-primary m-1" type="button" :disabled="currentIndex==3"
            @click="NextQuestions"><i class="fa fa-arrow-right" aria-hidden="true"></i></button>
        </form>
      </div>
    </div>
  </nav>
  <div class="border border-2 border-success p-1 shadow-sm mb-1 bg-body rounded">
    <div class="border border-3 border-primary p-1 shadow-sm mb-1 bg-body rounded">
      <RouterView :currentIndex="currentIndex" />
    </div>
  </div>

</template>

<style scoped>
  .fa-clock-o {
    font-size: 25px;
  }

  .content {
    border: 2px solid green;
    margin: 5px;
  }
</style>