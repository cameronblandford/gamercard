<template>
  <div class="container mt-5">
    <h1 class="text-center display-4 mb-5">Assignments</h1>

    <div class="row row-eq-height">
      <div class="col-md-6 offset-md-3">
        <b-button variant="link" size="sm" class="text-muted">Show completed</b-button>
        <b-card
          v-for="a in assignments"
          :key="a.id"
          :title="a.title"
          :class="'mb-4 ' + (!a.active ? 'inactive' : null)"
        >
          <div v-if="a.active">
            <b-card-text class="lead">{{a.shortDescription}}</b-card-text>
            <b-card-text>{{a.description.length > 300 ? a.description.substring(0, 300) + '...' : a.description}}</b-card-text>
            <!-- user is about to submit for first time -->
            <b-button
              v-if="a.canSubmit && a.active"
              :href="`/assignments/${a.id}`"
              variant="outline-success"
            >{{a.submitted ? 'Resubmit' : "Submit"}}</b-button>
            <!-- user has already made a submission but can submit again -->
            <div v-else-if="a.isQuiz">
              <b-button variant="outline-success">See Details</b-button>
              <b-button variant="outline-success">Take Quiz</b-button>
            </div>
            <b-button v-else-if="a.graded" variant="outline-secondary">Already graded</b-button>
          </div>
          <div v-else-if="!a.active && !a.graded">
            <b-card-text>{{a.description.length > 100 ? a.description.substring(0, 100) + '...' : a.description}}</b-card-text>
          </div>
        </b-card>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      assignments: [
        {
          id: 0,
          title: 'Getting Started',
          shortDescription: 'Syllabus Day Readings',
          description:
            "Welcome to class! Please read through the links listed on this page, take a quick quiz, and we'll give you a nice juicy A!",
          graded: false,
          submitted: false,
          canSubmit: false,
          active: true,
          isQuiz: true
        },
        {
          id: 1,
          title: 'Assignment 1',
          shortDescription: 'consectetur adipiscing elit',

          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          graded: true,
          submitted: true,
          canSubmit: true,
          active: true
        },
        {
          id: 2,
          title: 'Assignment 2',
          shortDescription: 'consectetur adipiscing elit',

          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          graded: false,
          submitted: false,
          canSubmit: true,
          active: true
        },
        {
          id: 3,
          title: 'Assignment 3',
          shortDescription: 'consectetur adipiscing elit',

          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          prereqs: ['Assignment 1', 'Assignment 2'],
          graded: false,
          submitted: false,
          canSubmit: true,
          active: false
        },
        {
          id: 4,
          title: 'Assignment 4',
          shortDescription: 'consectetur adipiscing elit',

          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          graded: false,
          submitted: false,
          canSubmit: true,
          active: false
        },
        {
          id: 5,
          title: 'Assignment 5',
          shortDescription: 'consectetur adipiscing elit',
          description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
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
