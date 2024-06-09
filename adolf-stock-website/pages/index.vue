<template>
  <div
    class="flex min-h-screen flex-col bg-[url('images/38d615_9af78986b2ca44cdbc93872bd31a3198~mv2.webp')] bg-cover"
  >
    <div class="px-4 py-8 lg:max-w-[50rem] lg:self-center">
      <h1 class="text-4xl md:text-6xl lg:text-8xl">
        NACH<span class="text-[#80885b]">GEFRAGT</span>
      </h1>
      <h2 class="text-3xl text-white">Das Interviewprojekt von Adolf Stock</h2>
      <h3 class="text-white lg:mt-40">Neue Interviews</h3>

      <div
        class="mx-4 flex flex-col gap-4 md:mx-0 md:grid md:grid-cols-2 lg:grid-cols-3"
      >
        <ContentQuery :path="'posts'">
          <template #default="{ data }">
            <NuxtLink
              :to="post._path"
              v-for="post of data"
              :key="post.title"
              class="flex flex-col border border-gray-300 bg-[#f3f4ee]"
            >
              <img :src="post.img" class="" />
              <div class="flex flex-col gap-3 p-4">
                <div class="text-xs">{{ post.author }}</div>
                <div>{{ post.title }}</div>
              </div>
            </NuxtLink>
          </template>
          <template #not-found>
            <p>No authors found.</p>
          </template>
        </ContentQuery>
      </div>
    </div>
  </div>
</template>
