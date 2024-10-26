<template>
    <v-container id="service" fluid>
      <h1 class="center-label text-h5 text-left mb-6">Skills & Services</h1>

      <v-carousel hide-delimiters>
        <v-carousel-item v-for="(skill, i) in skills" :key="i">
          <v-sheet height="100%" tile>
            <v-row class="fill-height" align="center" justify="center">
              <v-col cols="12" md="6" class="text-center">
                <v-img
                  :src="skill.image"
                  height="200"
                  contain
                  class="mb-4"
                ></v-img>
                <h2 class="skill-name">{{ skill.name }}</h2>
                <p class="skill-name">{{ skill.description }}</p>
              </v-col>
            </v-row>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
      <v-row>
        <v-col cols="12" md="6">
          <h2 class="stack-title mb-6">Frontend Frameworks/Libraries</h2>
          <div class="stack-container">
            <div v-for="(skill, index) in frontendSkills" :key="index" class="skill-row mb-4">
              <div class="d-flex align-center justify-space-between mb-1">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-percentage">{{ skill.percentage }}%</span>
              </div>
              <v-progress-linear
                :model-value="skill.percentage"
                height="10"
                rounded
                background-color="#e0f2f6"
                color="#a7d5e1"
              ></v-progress-linear>
            </div>
          </div>
        </v-col>

        <v-col cols="12" md="6">
          <h2 class="stack-title mb-6">Backend Frameworks/Database</h2>
          <div class="stack-container">
            <div v-for="(skill, index) in backendSkills" :key="index" class="skill-row mb-4">
              <div class="d-flex align-center justify-space-between mb-1">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-percentage">{{ skill.percentage }}%</span>
              </div>
              <v-progress-linear
                :model-value="skill.percentage"
                height="10"
                rounded
                background-color="#e0f2f6"
                color="#a7d5e1"
              ></v-progress-linear>
            </div>
          </div>
        </v-col>
      </v-row>
      <v-row justify="center"> <!-- Changed this row -->
        <v-col cols="12" md="6"> <!-- Added column with medium size 6 -->
          <h2 class="stack-title mb-6">Other Known Languages</h2>
          <div class="stack-container">
            <div v-for="(skill, index) in otherlanguages" :key="index" class="skill-row mb-4">
              <div class="d-flex align-center justify-space-between mb-1">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-percentage">{{ skill.percentage }}%</span>
              </div>
              <v-progress-linear
                :model-value="skill.percentage"
                height="10"
                rounded
                background-color="#e0f2f6"
                color="#a7d5e1"
              ></v-progress-linear>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    name: 'ServiceSection',
    data: () => ({
      skills: [
        {
          name: 'Backend Skills',
          icon: 'mdi-web',
          description: 'Through my academic experiences, I have developed a solid foundation in backend development, enabling me to efficiently manage server-side operations and data management.',
          image: require('@/assets/backend.png')
        },
        {
          name: 'Frontend Skills',
          icon: 'mdi-chart-bar',
          description: 'Specializes in designing user interfaces that are both visually engaging and easy to navigate by the old and new users.',
          image: require('@/assets/frontend.png')
        },
        {
          name: 'Data Analytics',
          icon: 'mdi-palette',
          description: 'Specialize in reading and analyzing data records, with expertise in interpreting and extracting valuable insights to support any decision-making.',
          image: require('@/assets/database.png')
        },
        {
          name: 'Writing',
          icon: 'mdi-palette',
          description: 'In addition to my technical expertise, I possess strong writing skills, creating essays, poems, and various forms of literary content with resilience and creativity.',
          image: require('@/assets/writing.png')
        },
        {
          name: 'Reading',
          icon: 'mdi-palette',
          description: 'Good in proofreading and providing thoughtful feedback and insights to enhance the quality of your chosen material and help you with your assignment.',
          image: require('@/assets/reading.png')
        }
        
      ],

      frontendSkills: [
      { name: 'Bootstrap', percentage: 90 },
      { name: 'Tailwind', percentage: 60 },
      { name: 'Vuetify', percentage: 85 },
      { name: 'Vue.js', percentage: 70 }
      ],
      backendSkills: [
        { name: 'Laravel', percentage: 80 },
        { name: 'PostgreSQL', percentage: 100 },
        { name: 'Supabase', percentage: 70 },
        { name: 'MySQL', percentage: 95 }
      ],
      otherlanguages: [
      { name: 'C', percentage: 79 },
      { name: 'Java', percentage: 80 },
        { name: 'Python', percentage: 75 },
        { name: 'JavaScript', percentage: 50 },
        { name: 'PHP', percentage: 100 },
        { name: 'HTML/CSS', percentage: 89 },
        { name: 'Go', percentage: 65 }
      ]
    })
  }
  </script>

  <style scoped>
    .center-label{
      font-family: Garamond;
      color: #a7d5e1;
      text-decoration: underline;
    }

    .stack-title {
    font-family: Garamond;
    color: #a7d5e1;
    font-size: 1.8rem;
    font-weight: 500;
  }

  .stack-container {
    padding: 0 10px;
  }

  .skill-row {
    margin-bottom: 1.5rem;
  }

  .skill-name {
    font-family: Garamond;
    color: #a7d5e1;
    font-size: 1.1rem;
    font-weight: 500;
  }

  .skill-percentage {
    font-family: Garamond;
    color: #a7d5e1;
    font-weight: 500;
  }

  /* progress bars more dark */
  :deep(.v-progress-linear__determinate) {
    transition: width 0.5s ease-in-out;
  }

  /* hover effect to the skill rows */
  .skill-row:hover .v-progress-linear__determinate {
    filter: brightness(0.95);
  }

  @media (max-width: 600px) {
    .stack-title {
      font-size: 1.5rem;
    }
    
    .skill-name {
      font-size: 1rem;
    }
  }

  /*skills row hover */
  :deep(.v-img) {
    border-radius: 8px;
    transition: transform 0.3s ease;
  }

  :deep(.v-img:hover) {
    transform: scale(1.05);
  }
  </style>