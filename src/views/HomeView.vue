<script setup>
  import HelloWorld from '@/components/HelloWorld.vue';
  import QuizOne from '@/components/QuizOne.vue';
  import QuizTwo from '@/components/QuizTwo.vue';
</script>

<template>
  <HelloWorld v-if="currentIndex==1"/>
  <QuizOne v-if="currentIndex==2"/>
  <QuizTwo v-if="currentIndex==3"/>
</template>


<script>
  export default {
    data() {
      return {

      }
    },
    props: {
      currentIndex: {
        type: Number,
        required: true
      }
    }
  }
</script>