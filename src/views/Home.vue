<template>
  <!-- <HelloWorld /> -->
  <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
  <h5>{{ code || "READ A CODEBAR" }}</h5>
</template>

<script setup>
// import HelloWorld from '@/components/HelloWorld.vue'
import { ref } from "vue";
import { StreamBarcodeReader } from "vue-barcode-reader";

const code = ref(null);

const onDecode = (text) => {
  code.value = text;
  console.log(`Decode text from QR code is ${text}`)
}
const onLoaded = () => {

  console.log(`Ready to start scanning barcodes`)
}

</script>
