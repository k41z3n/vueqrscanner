<template>
  <!-- <HelloWorld /> -->
  <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
  <v-alert class="text-center">{{ code || "READ A CODEBAR" }}</v-alert>
  <br>
  <h6 class=text-center>{{ version }}</h6>
</template>

<script setup>
// import HelloWorld from '@/components/HelloWorld.vue'
import { ref } from "vue";
import { StreamBarcodeReader } from "vue-barcode-reader";

const code = ref(null);

const version = __APP_VERSION__

const onDecode = (text) => {
  code.value = text;
  console.log(`Decode text from QR code is ${text}`)
}
const onLoaded = () => {

  console.log(`Ready to start scanning barcodes`)
}

</script>
