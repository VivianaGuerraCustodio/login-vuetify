<template>
  <v-app>
    <v-main>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="8" md="8">
            <v-card class="elevation-12">
              <v-window v-model="step">
                <v-window-item :value="1">
                  <v-row>
                    <v-col cols="12" md="8">
                      <v-card-text class="mt-12">
                        <h2
                          class="text-center display-2 p-3 m-3 teal--text text--acent-3"
                        >
                          CTI te la bienvenida
                        </h2>
                        <div class="text-center" mt-4>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon> fab fa-facebook-f </v-icon>
                          </v-btn>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon> fab fa-google-plus-g </v-icon>
                          </v-btn>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon> fab fa-linkedin-in </v-icon>
                          </v-btn>
                        </div>
                        <h4 class="text-center mlt-4">
                          Ingresa tus credenciales
                        </h4>
                        <v-form>
                          <v-text-field
                            v-model="correo"
                            required
                            label="Email"
                            name="Email"
                            prepend-icon="email"
                            type="email"
                            color="teal darken-3"
                          />
                          <v-text-field
                            required
                            v-model="contraseña"
                            id="password"
                            label="Password"
                            name="Password"
                            prepend-icon="lock"
                            type="password"
                            color="teal darken-3"
                          />
                        </v-form>
                        <h5 class="text-center mt-3">
                          Olvidaste tu contraseña?
                        </h5>
                      </v-card-text>
                      <div class="text-center mt-3">
                        <v-btn
                          rounded
                          color="teal darken-3"
                          dark
                          @click="goToMenu"
                          >Iniciar sesión</v-btn
                        >
                      </div>
                    </v-col>
                    <v-col cols="12" md="4" class="teal darken-3">
                      <v-card-text class="white--text mt-12">
                        <h1 class="text-center display-1">Hola amigos</h1>
                        <h5 class="text-center">
                          Ingresa tus datos personales y ¡ Empieza el viaje con
                          nosotros !
                        </h5>
                      </v-card-text>
                      <div class="text-center">
                        <v-btn rounded outlined="" dark @click="step++"
                          >Registrate</v-btn
                        >
                      </div>
                    </v-col>
                  </v-row>
                </v-window-item>
                <v-window-item :value="2">
                  <v-row class="fill-height">
                    <v-col cols="12" md="4" class="teal darken-3">
                      <v-card-text class="white--text mt-12">
                        <h3 class="text-center display-1">
                          Bienvenido de nuevo
                        </h3>
                        <h5 class="text-center">
                          Se siente bien tenerte aqui
                        </h5>
                      </v-card-text>
                      <div class="text-center">
                        <v-btn rounded outlined="" dark @click="step--"
                          >Iniciar Sesión</v-btn
                        >
                      </div>
                    </v-col>
                    <v-col cols="12" md="8">
                      <v-card-text class="mt-12">
                        <h1
                          class="text-center display-2 teal--text text--darken-3"
                        >
                          Crear cuenta
                        </h1>
                        <div class="text-center" mt-4>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon> fab fa-facebook-f </v-icon>
                          </v-btn>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon> fab fa-google-plus-g </v-icon>
                          </v-btn>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon> fab fa-linkedin-in </v-icon>
                          </v-btn>
                        </div>
                        <h4 class="text-center mt-4">
                          Ingresa tus datos para el registro
                        </h4>
                        <v-form>
                          <v-text-field
                            label="Name"
                            name="Name"
                            prepend-icon="person"
                            type="text"
                            color="teal darken-3"
                          />
                          <v-text-field
                            label="Email"
                            name="Email"
                            prepend-icon="email"
                            type="text"
                            color="teal darken-3"
                          />
                          <v-text-field
                            id="password"
                            label="Password"
                            name="Password"
                            prepend-icon="lock"
                            type="text"
                            color="teal darken-3"
                          />
                        </v-form>
                      </v-card-text>
                      <div class="text-center mt-n5">
                        <v-btn rounded outlined="" color="teal darken-3" dark
                          >Registrar</v-btn
                        >
                      </div>
                    </v-col>
                  </v-row>
                </v-window-item>
              </v-window>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>
<script>
export default {
  data: () => ({
    step: 1,
    correo: "",
    contraseña: ""
  }),
  props: {
    source: String
  },
  methods: {
    goToMenu() {
      if (this.correo == "" || this.contraseña == "") {
        alert("Llenar los campos sugeridos");
      } else if (
        this.correo !== "" &&
        this.correo.includes("@") &&
        this.correo.includes(".")
      ) {
        this.$router.replace({
          path: "/about"
        });
      } else {
        alert("email no valido");
      }
    }
  }
};
</script>