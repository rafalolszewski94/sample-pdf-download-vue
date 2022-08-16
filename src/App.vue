<script setup>
import { saveAs } from "file-saver";

const pdfUrl = "/TestPDFfile.pdf";

const download = () => {
  fetch(pdfUrl)
    .then((res) => res.blob())
    .then((blob) => {
      console.log(blob);
      saveAs(blob);
    });
};
</script>

<template>
  <div>
    <button @click="download">download pdf</button>
  </div>
</template>
