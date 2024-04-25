<template>
  <div class="item">
    <div class="icon">
      <slot name="icon"></slot>
    </div>
    <div class="wrapper">
      <slot name="title"></slot>
      <slot name="text"></slot>
    </div>
  </div>
</template>

<style scoped>
.item {
  display: flex;
  gap: 30px;
}
</style>