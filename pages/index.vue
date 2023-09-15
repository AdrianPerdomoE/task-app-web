<template>
  <div style="display: flex; flex-direction: column; align-items: center; justify-content: center;">

    <h1>Bienvenidos a la app de tareas</h1>
    <p>Esta es una aplicación que permite gestionar las tareas de los estudiantes</p>
    <h1>Login</h1>

    <div>

      <v-card class="mx-auto pa-12 pb-8" elevation="8" max-width="448" rounded="lg">
        <div class="text-subtitle-1 text-medium-emphasis">Cuenta</div>

        <v-text-field density="compact" placeholder="Email address" prepend-inner-icon="mdi-email-outline"
          variant="outlined" v-model="correo"></v-text-field>

        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between">
          Contraseña
        </div>

        <v-text-field :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'" :type="visible ? 'text' : 'password'"
          density="compact" placeholder="Enter your password" prepend-inner-icon="mdi-lock-outline" variant="outlined"
          @click:append-inner="visible = !visible" style="width: 300px;" v-model="pass"></v-text-field>



        <v-btn block class="mb-8" color="blue" size="large" variant="tonal" @click="Ingresar()">
          Ingresar
        </v-btn>
      </v-card>
    </div>
  </div>
</template>
<script setup>

const pass = ref("");
const correo = ref("");
const visible = ref(false);
const Router = useRouter();
const user = {
  "name": "Prueba",
  "clave": 1234,
  "correo": "a@gmail.com"
}
const Ingresar = () => {
  console.log(pass)
  if (pass.value == user.clave && correo.value == user.correo) { Router.push({ path: "/tareas" }) }
  else { alert('Datos invalidos') }
}

definePageMeta({
  layout: "blank"
});
</script>