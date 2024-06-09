<template>
  <div
    class="flex flex-col border-y border-gray-300 bg-[#efefef] p-4 shadow-sm"
  >
    <nav class="self-center lg:max-w-[50rem]">
      <ul class="flex flex-row gap-4 md:gap-6 lg:gap-8">
        <li
          class="flex items-center hover:text-green-600 focus:text-gray-700"
          v-for="link in links"
          :key="link.route"
        >
          <nuxt-link
            class="my-2 uppercase sm:text-lg md:my-3 md:text-xl lg:my-4 lg:text-2xl"
            :to="`${link.route}`"
          >
            {{ link.label }}
          </nuxt-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
const links = [
  {
    label: "Start",
    route: "/",
  },
  {
    label: "Interviews",
    route: "/blog",
  },
  {
    label: "Projekt",
    route: "/das-projekt",
  },
];

export default {
  data() {
    return {
      links: links,
    };
  },
};
</script>

<style>
a.nuxt-link-exact-active {
  @apply text-gray-700;
}
</style>
