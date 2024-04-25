<script setup>
import IconDocumentationVue from "./icons/IconDocumentation.vue";
import IconCommunity from "./icons/IconCommunity.vue";
import IconEcosystem from "./icons/IconEcosystem.vue";
import IconTooling from "./icons/IconTooling.vue";
import IconSupport from "./icons/IconSupport.vue";
import WelcomeItem from "./WelcomeItem.vue";
</script>


<template>
  <WelcomeItem>
    <template #icon>
      <IconDocumentationVue/>
    </template>

    <template #title>Documentation</template>
    <template #text>Vue’s
      <a href="https://vuejs.org/" target="_blank" rel="noopener">official documentation</a>
      provides you with all information you need to get started.</template>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <IconCommunity/>
    </template>

    <template #title>Community</template>
    <template #text>Vue’s
      <a href="https://vuejs.org/" target="_blank" rel="noopener">official documentation</a>
      provides you with all information you need to get started.</template>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <IconEcosystem/>
    </template>

    <template #title>Community</template>
    <template #text>Vue’s
      <a href="https://vuejs.org/" target="_blank" rel="noopener">official documentation</a>
      provides you with all information you need to get started.</template>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <IconTooling/>
    </template>

    <template #title>Community</template>
    <template #text>Vue’s
      <a href="https://vuejs.org/" target="_blank" rel="noopener">official documentation</a>
      provides you with all information you need to get started.</template>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <IconSupport/>
    </template>

    <template #title>Community</template>
    <template #text>Vue’s
      <a href="https://vuejs.org/" target="_blank" rel="noopener">official documentation</a>
      provides you with all information you need to get started.</template>
  </WelcomeItem>
</template>