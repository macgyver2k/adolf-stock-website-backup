<template>
  <div>
    <ContentDoc>
      <template v-slot="{ doc }">
        <ContentRendererMarkdown :value="doc" />
      </template>
    </ContentDoc>
  </div>
</template>
