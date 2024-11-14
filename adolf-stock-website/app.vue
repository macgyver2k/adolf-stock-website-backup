<template>
  <div class="flex flex-col">
    <NavBar class="sticky top-0" />
    <NuxtPage style="min-height: calc(100vh - 12rem)" />
    <Footer />
  </div>
</template>

<style lang="scss">
body {
  padding: 0;
  margin: 0;
  @apply font-sans;
}
</style>
