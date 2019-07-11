<template>
  <div class="container mt-5">
    <h1 class="text-center display-4 mb-5">Assignments</h1>
    <b-button variant="link" class="text-center text-muted w-100">See Completed</b-button>
    <div class="row row-eq-height">
      <b-card
        v-for="a in assignments"
        :key="a.id"
        :title="a.title"
        :class="'mb-4 col-md-6 offset-md-3 ' + (!a.active ? 'inactive' : null)"
      >
        <b-card-text>{{a.description}}</b-card-text>
        <!-- user is about to submit for first time -->
        <b-button
          v-if="a.canSubmit && !a.submitted && a.active"
          href="#"
          variant="outline-success"
        >Submit</b-button>
        <!-- user has already made a submission but can submit again -->
        <b-button
          v-else-if="a.canSubmit && a.submitted && a.active"
          variant="outline-success"
        >Resubmit</b-button>
        <b-button v-else-if="a.graded" disabled variant="outline-secondary">Already graded</b-button>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      assignments: [
        {
          id: 1,
          title: 'Assignment 1',
          description: 'Lorem ipsum...',
          graded: true,
          submitted: true,
          canSubmit: true,
          active: true
        },
        {
          id: 2,
          title: 'Assignment 2',
          description: 'Lorem ipsum...',
          graded: false,
          submitted: false,
          canSubmit: true,
          active: true
        },
        {
          id: 3,
          title: 'Assignment 3',
          description: 'Lorem ipsum...',
          prereqs: ['Assignment 1', 'Assignment 2'],
          graded: false,
          submitted: false,
          canSubmit: true,
          active: false
        },
        {
          id: 4,
          title: 'Assignment 4',
          description: 'Lorem ipsum...',
          graded: false,
          submitted: false,
          canSubmit: true,
          active: false
        }
      ]
    }
  }
}
</script>

<style scoped>
.inactive {
  opacity: 0.5;
}
</style>
