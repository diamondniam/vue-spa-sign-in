<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
<div class="container">
  <div class="header">
    <div class="nav">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/sign-in">Sign-in</RouterLink>
    </div>
  </div>

  <div class="wrapper">
    <RouterView></RouterView>
  </div>
</div>
</template>