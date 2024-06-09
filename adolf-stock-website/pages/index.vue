<template>
  <div class="min-h-screen bg-[url('images/mic.jpg')] bg-cover">
    <h1 class="text-5xl">NACH<span class="text-[#80885b]">GEFRAGT</span></h1>
    <h2 class="text-3xl text-white">Das Interviewprojekt von Adolf Stock</h2>
    <h3 class="text-white">Neue Interviews</h3>

    <div class="mx-4 flex flex-col gap-4">
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
</template>
