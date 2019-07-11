<template>
  <div class="container">
    <div class="row">
      <div class="col-lg-8">
        <div class="assignment-title">
          <h1>Assignment Name</h1>
          <p class="lead">This is the (short) description of the assignment.</p>
        </div>
        <div class="assignment-body">
          <h2>Goals</h2>
          <p class="lead">To learn how to do the things the assignment is supposed to teach you.</p>
          <h2>Win Condition</h2>
          <p
            class="lead"
          >Finish the assignment and submit it below. Your TA will tell you if you did good or not.</p>
          <div class="upload-area">
            <b-form-file
              v-model="files"
              :state="Boolean(files.length)"
              multiple
              placeholder="Browse or drag your files here"
              drop-placeholder="Drop files here..."
            ></b-form-file>
          </div>
          <h2>Additional Resources</h2>
          <ul>
            <li>Item</li>
            <li>Item</li>
            <li>Item</li>
            <li>Item</li>
          </ul>
        </div>
      </div>
      <div class="col-lg-4">
        <h1>test</h1>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      files: []
    }
  }
}
</script>


<style scoped>
.assignment-title {
  margin-top: 30px;
  margin-bottom: 30px;
}
.upload-area {
  margin-bottom: 30px;
}
</style>