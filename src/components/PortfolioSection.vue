<template>
  <v-container id="portfolio" fluid>
    <h1 class="center-label text-h5 text-left mb-6">Works & Projects</h1>
    <v-row>
      <v-col v-for="(project, index) in projects" :key="project.title" cols="12" sm="6" md="4">
        <v-card class="project-card">
          <v-img :src="project.image" height="200px" cover></v-img>
          <v-card-title class="project-title">{{ project.title }}</v-card-title>
          <v-card-text class="project-description">{{ project.description }}</v-card-text>
          <v-card-actions>
            <v-btn class="button" text @click="openModal(index)">View Project</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>

    <!--Modal here -->
    <v-dialog v-model="dialog" max-width="500">
      <v-card v-if="selectedProject">
        <v-card-title class="text-h5 project-modal-title d-flex align-center">
          <div class="mr-auto">{{ selectedProject.title }}</div>
          <v-btn icon @click="dialog = false">
            <v-icon class="close">mdi-close</v-icon>
          </v-btn>
        </v-card-title>

        <v-card-text class="project-modal-content">
          <v-list>
            <v-list-item>
              <v-list-item-title class="modal-label">Members:</v-list-item-title>
              <v-list-item-subtitle>{{ selectedProject.members }}</v-list-item-subtitle>
            </v-list-item>

            <v-list-item>
              <v-list-item-title class="modal-label">Date Started:</v-list-item-title>
              <v-list-item-subtitle>{{ selectedProject.dateStarted }}</v-list-item-subtitle>
            </v-list-item>

            <v-list-item>
              <v-list-item-title class="modal-label">Date Finished:</v-list-item-title>
              <v-list-item-subtitle>{{ selectedProject.dateFinished }}</v-list-item-subtitle>
            </v-list-item>

            <v-list-item>
              <v-list-item-title class="modal-label">Instructor:</v-list-item-title>
              <v-list-item-subtitle>{{ selectedProject.instructor }}</v-list-item-subtitle>
            </v-list-item>
          </v-list>
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            class="button mb-4"
            text
            :href="selectedProject.link"
            target="_blank"
          >
            Visit Project
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
export default {
  name: 'PortfolioSection',
  data: () => ({
    dialog: false,
    selectedProject: null,
    projects: [
      {
        title: 'IT 106 Final Project',
        description: 'Client-Server Java RMI and XML Parsing with Laravel for the Shared Database as an intergration method',
        image: require('@/assets/IT106-finals.png'),
        link: '#',
        members: 'Eden Grace Bughao, Leoneil Ivan Aying, Prince Nino Antigo',
        dateStarted: 'May 7, 2024',
        dateFinished: 'May 23, 2024',
        instructor: 'Dexter Romaguera'
      },
      {
        title: 'ITE 18 Midterm Project',
        description: 'A Mcdo-inspired online food service using PHP to perform the CRUD operations to the PSQL database',
        image: require('@/assets/108-finals-feed.png'),
        link: '#',
        members: 'Eden Grace Bughao, Leoneil Ivan Aying, Prince Nino Antigo',
        dateStarted: 'March 2, 2024',
        dateFinished: 'April 14, 2024',
        instructor: 'Karl Vincent Panase'
      },
      {
        title: 'Summer Project',
        description: 'Own book review website design using Bootstrap framework named Bookish. Intended as a personal blog and a personal exercise in Bootstrap',
        image: require('@/assets/summerproject.png'),
        link: '#',
        members: 'Eden Grace Bughao',
        dateStarted: 'August 9, 2024',
        dateFinished: 'August 31, 2024',
        instructor: 'N/A'
      },
      {
        title: 'ITE 18 Project Assignment',
        description: 'Simple CRUD Applications using PHP, named Foodee for the concept of food delivery services.',
        image: require('@/assets/108-midterm.png'),
        link: '#',
        members: 'Eden Grace Bughao, Leoneil Ivan Aying, Prince Nino Antigo',
        dateStarted: 'February 8, 2024',
        dateFinished: 'February 23, 2024',
        instructor: 'Karl Vincent Panase'
      },
      {
        title: 'IT 110 Project Assignment',
        description: 'Single Page Application (SPA) that functions as a To-Do List Scheduling tool. Utilize VueJS and integrate Vuetify. Deployed using Vercel.',
        image: require('@/assets/110todolist.png'),
        link: 'https://vercel.com/api/toolbar/link/todolist-amber-eight.vercel.app?via=team-dashboard-project-entity&p=1&page=/',
        members: 'Eden Grace Bughao',
        dateStarted: 'September 4, 2024',
        dateFinished: 'September 19, 2024',
        instructor: 'John Michael Cutamora'
      },
      {
        title: 'ITE 18 Project Assignment',
        description: 'Personalized Calculator Using Javascript. Manipulation of Document Object Model (DOM) to dynamically update content based on user actions.',
        image: require('@/assets/108-jscalculator.png'),
        link: '#',
        members: 'Eden Grace Bughao, Leoneil Ivan Aying, Prince Nino Antigo',
        dateStarted: 'January 23, 2023',
        dateFinished: 'January 26, 2024',
        instructor: 'Karl Vincent Panase'
      }
    ]
  }),
  methods: {
    openModal(index) {
      this.selectedProject = this.projects[index];
      this.dialog = true;
    }
  }
}
</script>

<style scoped>
#portfolio {
  background-color: #a7d5e1;
}

.center-label {
  font-family: Garamond;
  color: white;
  text-decoration: underline;
}

.project-card {
  background-color: white;
}

.project-title,
.project-description {
  color: #a7d5e1;
}

.button {
  background-color: #a7d5e1;
  color: white;
}

.project-modal-title {
  background-color: #a7d5e1;
  color: white;
  font-family: Garamond;
}

.project-modal-content {
  padding: 20px;
}

.modal-label {
  color: #a7d5e1;
  font-weight: bold;
  font-family: Garamond;
}

.v-list-item-subtitle {
  color: #666 !important;
  font-family: Garamond;
}

.close{
  color: #a7d5e1;
}
</style>