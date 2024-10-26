<template>
  <v-container id="hireme" fluid>
    <h1 class="center-label text-h5 text-left mb-6">Collaborate with me</h1>
    <v-row justify="center" align="center" class="contact-row">
      <!-- contact information -->
      <v-col cols="12" md="6">
        <v-card class="contact-card pa-6">
          <v-card-title class="text-h4 mb-6">Get in touch</v-card-title>
          
          <!-- email -->
          <v-list-item class="mb-4">
            <v-list-item-avatar>
              <v-icon color="#a7d5e1">mdi-email</v-icon>
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="contact-label">Email</v-list-item-title>
              <v-list-item-subtitle>
                <a href="mailto:edengrace@gmail.com" class="contact-link">
                  edenbughao973@gmail.com
                </a>
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <!-- phone -->
          <v-list-item class="mb-4">
            <v-list-item-avatar>
              <v-icon color="#a7d5e1">mdi-phone</v-icon>
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="contact-label">Phone</v-list-item-title>
              <v-list-item-subtitle>
                <a 
                  href="https://wa.me/+639157674432" 
                  target="_blank" 
                  class="contact-link"
                >
                  +63 915 767 4432
                </a>
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <!-- address -->
          <v-list-item>
            <v-list-item-avatar>
              <v-icon color="#a7d5e1">mdi-map-marker</v-icon>
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="contact-label">Address</v-list-item-title>
              <v-list-item-subtitle>
                <a 
                  href="https://maps.google.com/?q=Lumina+Homes,+Taguibo,+Butuan+City" 
                  target="_blank"
                  class="contact-link"
                >
                  Lumina Homes, Taguibo, Butuan City
                </a>
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-col>

      <!-- GIF -->
      <v-col cols="12" md="6" class="text-center">
        <v-img
          :src="require('@/assets/contacts.gif')"
          alt="Contact Animation"
          contain
          height="400"
          class="gif"
        ></v-img>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'ContactSection'
}
</script>

<style scoped>
#hireme {
  background-color: #a7d5e1;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.center-label {
  font-family: Garamond;
  color: white;
  text-decoration: underline;
  margin-bottom: 2rem;
}

.contact-row {
  flex-grow: 1;
  margin-bottom: 0 !important; /* margin at the bottom */
}

.contact-card {
  background-color: white !important;
  border-radius: 10px;
}

.contact-label {
  font-family: Garamond;
  color: #a7d5e1 !important;
  font-weight: bold;
}

.contact-link {
  color: #666;
  text-decoration: none;
  transition: color 0.3s ease;
}

.contact-link:hover {
  color: #a7d5e1;
  text-decoration: underline;
}

.v-card-title {
  font-family: Garamond;
  color: #a7d5e1 !important;
}

/* animation for contact infos */
.v-list-item {
  transition: transform 0.3s ease;
}

.v-list-item:hover {
  transform: translateX(10px);
}

/* GIF responsiveness */
.v-img {
  max-width: 100%;
  height: auto;
}

@media (max-width: 960px) {
  .v-img {
    margin-top: 2rem;
    height: 300px;
  }
}

.gif{
  border-radius: 25%;
}
</style>
