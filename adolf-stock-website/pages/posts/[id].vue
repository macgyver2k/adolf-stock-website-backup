<template>
  <div class="flex flex-col gap-4">
    <ContentDoc>
      <template v-slot="{ doc }">
        <div class="flex flex-col gap-3">
          <div class="text-xs">{{ doc.author }}</div>
          <h1>{{ doc.title }}</h1>
        </div>
        <div class="flex flex-col">
          <iframe
            :src="doc.youtube"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            referrerpolicy="strict-origin-when-cross-origin"
            allowfullscreen
          ></iframe>

          <!-- <img :src="doc.img" /> -->
          <div>Foto: © {{ doc.img_copyright }}</div>
        </div>
        <ContentRendererMarkdown :value="doc" />
      </template>
      <template #not-found>
        <p>No authors found.</p>
      </template>
      <template #empty>
        <p>Post is empty.</p>
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
