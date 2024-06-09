<template>
  <div class="px-4 py-8 lg:max-w-[50rem] lg:self-center">
    <ContentDoc>
      <template v-slot="{ doc }">
        <ContentRendererMarkdown :value="doc" />
      </template>
    </ContentDoc>
  </div>
</template>
