<template>
  <div class="flex flex-col gap-4 px-4 py-8 lg:max-w-[50rem] lg:self-center">
    <ContentDoc>
      <template v-slot="{ doc }">
        <div class="flex flex-col gap-3">
          <div class="text-xs">{{ doc.author }}</div>
          <h1>{{ doc.headline }}</h1>
        </div>
        <div class="flex flex-col">
          <iframe
            v-if="doc.youtube"
            :src="doc.youtube"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            referrerpolicy="strict-origin-when-cross-origin"
            allowfullscreen
            class="h-48 sm:h-96"
          ></iframe>

          <div v-if="doc.img_copyright">
            Foto: © {{ doc.img_copyright }}
            <ContentRendererMarkdown :value="doc.img_copyright" />
          </div>
        </div>
        <ContentRendererMarkdown :value="doc" />
      </template>
      <template #not-found>
        <p>Dieser Beitrag extiert nicht.</p>
      </template>
      <template #empty>
        <p>Dieser Beitrag hat noch keinen Inhalt.</p>
      </template>
    </ContentDoc>
  </div>
</template>

<style>
p {
  @apply my-4;
}

p > a {
  @apply text-green-600 underline;
}
</style>
