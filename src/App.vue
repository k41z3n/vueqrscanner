<template>
  <router-view />
  
  <v-snackbar
    v-model="snackbar"
    color="primary"
    vertical
    location="bottom right"
    :timeout="-1"
  >
    <div class="text-subtitle-1 pb-2">
      New content available, click on reload button to update.
    </div>

    <template v-slot:actions>
      <v-btn color="success" variant="text" @click="updateServiceWorker"> Reload </v-btn>
      <v-btn color="danger" variant="text" @click="snackbar = false"> Close </v-btn>
    </template>
  </v-snackbar>
</template>

<script setup>
import { ref, watchEffect } from "vue";
import { useRegisterSW } from "virtual:pwa-register/vue";
const snackbar = ref(true);



const { needRefresh, updateServiceWorker } = useRegisterSW();

watchEffect(() => {
  if (needRefresh.value) snackbar.value = true;
  else snackbar.value = false;
});

</script>
