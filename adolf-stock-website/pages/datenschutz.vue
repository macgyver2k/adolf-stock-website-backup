<template>
  <div>
    <ContentDoc>
      <template v-slot="{ doc }">
        <ContentRendererMarkdown :value="doc" />
      </template>
    </ContentDoc>
  </div>
</template>

<style>
ul {
  @apply ml-6;
}

ul > li {
  @apply list-disc;
}
</style>
