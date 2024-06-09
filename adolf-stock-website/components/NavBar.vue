<template>
  <nav class="border-b p-4">
    <ul class="flex flex-row gap-2">
      <li
        class="flex items-center hover:text-green-600 focus:text-gray-700"
        v-for="link in links"
        :key="link.route"
      >
        <nuxt-link
          class="my-2 uppercase md:my-4 lg:my-0"
          @focusout="hide()"
          :to="`${link.route}`"
        >
          {{ link.label }}
        </nuxt-link>
      </li>
    </ul>
  </nav>
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
