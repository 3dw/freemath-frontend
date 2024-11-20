<template>
  <div class="about">
    <h1>數學題目列表</h1>
    <div v-if="loading">載入中...</div>
    <div v-else-if="error">發生錯誤: {{ error }}</div>
    <table v-else>
      <thead>
        <tr>
          <th>ID</th>
          <th>單元</th>
          <th>等級</th>
          <th>題目</th>
          <th>正確答案</th>
          <th>錯誤答案1</th>
          <th>錯誤答案2</th>
          <th>錯誤答案3</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="quiz in quizData" :key="quiz.id">
          <td>{{ quiz.id }}</td>
          <td>{{ quiz.unit }}</td>
          <td>{{ quiz.level }}</td>
          <td>{{ quiz.question }}</td>
          <td>{{ quiz.correct_answer }}</td>
          <td>{{ quiz.wrong_answer1 }}</td>
          <td>{{ quiz.wrong_answer2 }}</td>
          <td>{{ quiz.wrong_answer3 }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      quizData: [],
      loading: true,
      error: null
    }
  },
  async created() {
    try {
      const response = await axios.get('https://freemath-backend.alearn13994229.workers.dev/api/quizs/%E5%8A%A0%E6%B3%95')
      this.quizData = response.data
    } catch (err) {
      this.error = err.message
    } finally {
      this.loading = false
    }
  }
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    padding: 20px;
  }
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

th, td {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: left;
}
</style>
