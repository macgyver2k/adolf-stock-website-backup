<template>
  <div class="px-4 py-8 lg:max-w-[50rem] lg:self-center">
    <div class="flex flex-col gap-4 md:grid md:grid-cols-2 lg:grid-cols-3">
      <ContentQuery :path="'posts'" :sort="{ date: -1 }">
        <template #default="{ data }">
          <NuxtLink
            :to="post._path"
            v-for="post of data"
            :key="post.title"
            class="flex flex-col border border-gray-300 bg-[#f3f4ee] shadow-sm transition-shadow hover:border-gray-400 hover:shadow-md"
          >
            <img
              class="h-32 object-cover"
              :src="'/images' + post._path + '/' + post.img"
            />
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
