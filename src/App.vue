<script setup lang="ts">
import Header from "./components/Header.vue";
</script>

<template>
  <body class="w-full min-h-screen text-text">
    <Header></Header>
    <router-view />
  </body>
</template>
