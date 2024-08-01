<template>
  <v-app>
    <v-main class="main-background">
      <v-container fill-height>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="8" md="6">
            <v-card class="elevation-12 card-style">
              <v-card-title class="card-title">
                <v-img
                  src="@/assets/logosgamesblanco.png"
                  class="logo"
                  max-width="100"
                ></v-img>
              </v-card-title>
              <v-card-text>
                <h1 class="card-text">MANUAL DE USUARIO</h1>
              </v-card-text>
              <v-card-actions class="card-actions">
                <v-btn style="color: #121827" large @click="onButtonClick">Empezar</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  methods: {
    onButtonClick() {
      this.$router.push('Manual')

    }
  }
}
</script>



<style scoped>

 
@font-face {
    font-family: 'Answer';
    src: url('assets/fonts/Game Played.otf') format('truetype')
         ;
    font-weight: normal;
    font-style: normal;
  }
  
.main-background {
  background-image: url('@/assets/Fondoinicio.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  height: 100vh;
  margin: 0;
  padding: 0;
}

.card-style {
  padding: 20px;
  text-align: center;
  background-color: #121827; /* Fondo semitransparente */
  border-radius: 15px;
}

.card-title {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;

}

.logo {
  max-width: 100px;
}

.card-text {
  font-size: 28px;
  margin-bottom: 20px;
  color: white;
  font-family: 'Answer', sans-serif;
}

.card-actions {
  display: flex;
  justify-content: center;
}

.v-btn {
  font-size: 18px;
  padding: 10px 20px;
  color: white;
  font-family: 'Answer', sans-serif;
}
</style>
