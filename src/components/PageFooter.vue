<template>
    <v-footer color="#a7d5e1" dark>
      <v-container>
        <v-row justify="center" align="center">
          <v-col cols="12" class="text-center">
            <p>&copy; {{ new Date().getFullYear() }} E.Bughao. All rights reserved.</p>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </template>
  
  <script>
  export default {
    name: 'PageFooter'
  }
  </script>

  <style scoped>
    p{
      color: white;
    }
  </style>