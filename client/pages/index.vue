<template>
  <div class="container">
    <h1 class="text-center">Your Dashboard</h1>
    <div class="row">
      <div class="col-md-6">
        <h2>Upcoming Assignments</h2>
        <div class="card">
          <table class="table">
            <thead></thead>
            <tbody>
              <tr>
                <th>Name</th>
                <th>Type</th>
                <th>Due Date</th>
              </tr>
              <tr>
                <td>My New Assignment 1</td>
                <td>Quiz</td>
                <td>11/20/2019</td>
              </tr>
              <tr>
                <td>My New Assignment 2</td>
                <td>Homework</td>
                <td>11/20/2019</td>
              </tr>
              <tr>
                <td>My New Assignment 3</td>
                <td>Project</td>
                <td>12/31/2019</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
      <div class="col-md-6">
        <h2>Recent Grades</h2>
      </div>
    </div>
    <div class="row row-eq-height">
      <div class="col-sm-4">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Studying Resources</h5>
            <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
            <p
              class="card-text"
            >Some quick example text to build on the card title and make up the bulk of the card's content.</p>
            <a href="#" class="card-link">Card link</a>
            <a href="#" class="card-link">Another link</a>
          </div>
        </div>
      </div>
      <div class="col-sm-4">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Assignments</h5>
            <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
            <p
              class="card-text"
            >Some quick example text to build on the card title and make up the bulk of the card's content.</p>
            <a href="#" class="card-link">Card link</a>
            <a href="#" class="card-link">Another link</a>
          </div>
        </div>
      </div>
      <div class="col-sm-4">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Grades</h5>
            <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
            <p
              class="card-text"
            >Some quick example text to build on the card title and make up the bulk of the card's content.</p>
            <a href="#" class="card-link">Card link</a>
            <a href="#" class="card-link">Another link</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style scoped>
h1 {
  margin-top: 30px;
  margin-bottom: 30px;
}
h2 {
  text-align: center;
}
.card {
  margin-bottom: 30px;
}
</style>