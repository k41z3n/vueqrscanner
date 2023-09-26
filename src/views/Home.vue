<template>
  <!-- <HelloWorld /> -->
  <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
</template>

<script setup>
// import HelloWorld from '@/components/HelloWorld.vue'
import { StreamBarcodeReader } from "vue-barcode-reader";


const onDecode = (text) => {
  console.log(`Decode text from QR code is ${text}`)
}
const onLoaded = () => {
  console.log(`Ready to start scanning barcodes`)
}

</script>
