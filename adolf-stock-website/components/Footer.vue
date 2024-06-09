<template>
  <div
    class="flex flex-col border-y border-gray-300 bg-[#efefef] p-4 shadow-sm"
  >
    <nav class="self-center lg:max-w-[50rem]">
      <ul class="flex flex-row gap-2 border-b p-4">
        <li
          class="flex items-center hover:text-green-600 focus:text-gray-700"
          v-for="link in links"
          :key="link.route"
        >
          <nuxt-link
            class="my-2 uppercase md:my-4 lg:my-0"
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
    label: "Impressum",
    route: "/impressum",
  },
  {
    label: "Datenschutz",
    route: "/datenschutz",
  },
];

export default {
  data() {
    return {
      links: links,
      expanded: false, // Falls expanded ein Teil der Komponentendaten ist
    };
  },
  methods: {
    hide() {
      // Methode hide() implementieren, falls erforderlich
    },
  },
};
</script>

<style>
a.nuxt-link-exact-active {
  @apply text-gray-700;
}
</style>
