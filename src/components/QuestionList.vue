<template>
  <div class="container">
    <div class="border border-2 border-success p-1 shadow-sm mb-1 bg-body rounded">
      <div class="border border-3 border-primary p-1 shadow-sm mb-1 bg-body rounded">
        <div v-for="(question, index) in displayedQuestions" :key="index">
          <h5>Question {{ index + 1 }}:</h5>
          <p>{{ question.text }}</p>
        </div>
        <div class="d-flex justify-content-between mt-3">
          <button
            class="btn btn-primary"
            :disabled="currentPage === 1"
            @click="prevPage"
          >
            <i class="fa fa-arrow-left" aria-hidden="true"></i> Preview
          </button>
          <button
            class="btn btn-primary"
            :disabled="currentPage === totalPages"
            @click="nextPage"
          >
            Next <i class="fa fa-arrow-right" aria-hidden="true"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      questions: [
        { text: 'What is the capital of France?' },
        { text: 'What is 2 + 2?' },
        { text: 'What is the chemical symbol for gold?' },
        { text: 'What is the largest planet in our solar system?' },
        // Add more questions here
      ],
      currentPage: 1,
      questionsPerPage: 2,
    };
  },
  computed: {
    totalPages() {
      return Math.ceil(this.questions.length / this.questionsPerPage);
    },
    displayedQuestions() {
      const start = (this.currentPage - 1) * this.questionsPerPage;
      const end = start + this.questionsPerPage;
      return this.questions.slice(start, end);
    },
  },
  methods: {
    nextPage() {
      if (this.currentPage < this.totalPages) {
        this.currentPage += 1;
      }
    },
    prevPage() {
      if (this.currentPage > 1) {
        this.currentPage -= 1;
      }
    },
  },
};
</script>

<style scoped>
/* Add your custom styles here */
</style>
