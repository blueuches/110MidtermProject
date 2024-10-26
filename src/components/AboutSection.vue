<template>
    <v-container id="index" fluid>
      <h1 class="center-label text-h5 text-left mb-6">What about me?</h1>
      <v-row>
        <v-col cols="12" md="6">
          <h1 class="intro text-h1 mb-4">Hello World!</h1>
          <p class="mb-1">Full name: Eden Grace Moreno Bughao</p>
          <p class="mb-1">Nickname: Den</p>
          <p class="mb-1">Age: 21</p>
          <p class="mb-1">Birthday: September 7, 2003</p>
          <p class="mb-4">A third-year Information Technology student from Caraga State University, currently practicing and enhancing my skills to become a full-stack developer and data analyst. Driven by my dreams, I always conquer every academic challenge, no matter what.</p>
          <v-btn class="button" href="https://drive.google.com/drive/folders/1myCCclqph2IxcfRakLZgrprxIsUeYYo1?usp=sharing" target="_blank">View Certificates</v-btn>
        </v-col>
        <v-col cols="12" md="6">
          <v-img :src="profileImage" max-height="450" contain></v-img>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12">
          <v-card class="pa-6" outlined>
            <h2 class="text-h4 mb-6">Interests</h2>
            <v-chip-group
              class="interests-group"
              show-arrows
              column
            >
              <v-chip
                v-for="interest in interests"
                :key="interest"
                class="interest-chip ma-2 pa-4"
                large
                outlined
              >
                {{ interest }}
              </v-chip>
            </v-chip-group>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" class="text-center">
          <v-card class="pa-4">
            <v-icon x-large color="#a7d5e1" class="mb-4">mdi-format-quote-open</v-icon>
            <p class="text-h5 font-italic mb-4">"Don’t let the best parts of life pass you by because you’re too scared of the unknown.” One last wink. “Be cautiously reckless."</p>
            <p class="text-subtitle-1">Mikki Brammer</p>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>

  export default {
    name: 'AboutSection',
    data: () => ({
      profileImage: require('@/assets/aboutformal.png'),
      interests: ['Reading', 'History', 'Films', 'Music', 'Geography', 'Road Trips', 'Writing'],
    })
  }
  </script>

  <style scoped>
    .intro{
      font-family: Garamond;
      font-weight: bold;
      color: #a7d5e1;
    }

    .center-label{
      font-family: Garamond;
      color: #a7d5e1;
      text-decoration: underline;
    }

    h2,p{
      font-family: Garamond;
      color: #a7d5e1;
    }

    .button{
      background-color: #a7d5e1;
      color: white;
    }

    .interests-group {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      width: 100%;
    }
    .interest-chip {
      font-family: Garamond !important;
      font-size: 1.5rem !important;
      background-color: transparent !important;
      border: 2px solid #a7d5e1 !important;
      color: #a7d5e1 !important;
      transition: all 0.3s ease;
      min-width: 150px !important; /*minimum width */
      flex: 1 1 auto !important; /*chips to grow and shrink */
      text-align: center !important;
      margin: 8px !important; 
    }

    .interest-chip:hover {
      background-color: #a7d5e1 !important;
      color: white !important;
    }

    @media (max-width: 600px) {
      .interest-chip {
        font-size: 1rem !important;
        min-width: 120px !important;
        margin: 4px !important;
      }
    }
  </style>