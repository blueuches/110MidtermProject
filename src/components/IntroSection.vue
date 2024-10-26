<template>
  <v-container id="intro" fluid class="intro-container pa-0">
    <v-row no-gutters class="fill-height">
      <!-- left side -->
      <v-col cols="12" md="4" class="d-flex align-center">
        <div class="left-content">
          <h1 class="text-h2 mb-2">Welcome to my corner!</h1>
          <h2 class="text-h4 mb-4">I'm Eden</h2>
          <v-divider class="mb-4"></v-divider>
          <div class="social-media mb-4">
            <v-btn icon href="https://www.facebook.com/edenmoreno97/" target="_blank">
              <v-icon>mdi-facebook</v-icon>
            </v-btn>
            <v-btn icon href="https://github.com/blueuches" target="_blank">
              <v-icon>mdi-github</v-icon>
            </v-btn>
            <v-btn icon href="https://www.linkedin.com/in/eden-bughao-183b9532a/" target="_blank">
              <v-icon>mdi-linkedin</v-icon>
            </v-btn>
          </div>
        </div>
      </v-col>

      <!-- center -->
      <v-col cols="12" md="4" class="d-flex align-center justify-center">
        <div class="image-container">
          <div class="circle-background"></div>
          <v-img
            :src="profileImage"
            class="profile-image"
            :aspect-ratio="1"
            contain
          ></v-img>
        </div>
      </v-col>

      <!-- right side -->
      <v-col cols="12" md="4" class="d-flex align-center">
        <div class="right-content">
          <h1 class="text-h3 mb-2">Chronically online college student</h1>
          <h3 class="text-h5 mb-4">book hoarder • etymology enthusiast</h3>
          <p class="mb-4">Pursuing a degree in Information Technology at Caraga State University, with aspirations to become a web developer and data analyst.</p>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import profileImage from '@/assets/intropic.png'

export default {
  name: 'IntroSection',
  data() {
    return {
      profileImage
    }
  }
}
</script>

<style scoped>

*,h1,h2,h3{
  font-family: Garamond;
  background-color: #a7d5e1;
  color: white;
}

.intro-container {
  height: calc(100vh - 64px);
  min-height: 600px;
  overflow: hidden;
  position: relative;
}

.fill-height {
  height: 100%;
}

.left-content, .right-content {
  padding: 2rem;
  max-width: 400px;
}

.left-content {
  margin-left: auto;
  margin-right: 2rem;
}

.right-content {
  margin-left: 2rem;
  margin-right: auto;
}

.image-container {
  position: relative;
  width: 500px;
  height: 500px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.circle-background {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: #a7d5e1;
  border-radius: 50%;
  z-index: 1;
}

.profile-image {
  position: relative;
  z-index: 2;
  width: 100% !important;
  height: 100% !important;
  object-fit: cover;
}

/* responsiveness */
@media (max-width: 960px) {
  .intro-container {
    height: auto;
    padding: 2rem 0;
  }

  .left-content, .right-content {
    margin: 1rem auto;
    text-align: center;
    padding: 1rem;
  }

  .image-container {
    width: 300px;
    height: 300px;
    margin: 2rem auto;
  }

  .social-media {
    justify-content: center;
    display: flex;
  }
}

@media (min-width: 961px) {
  .v-col-md-4 {
    flex-basis: 33.333333% !important;
    max-width: 33.333333% !important;
  }
}
</style>