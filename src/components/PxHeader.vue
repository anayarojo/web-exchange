<template>
  <header class="shadow w-screen">
    <nav>
      <nav class="flex items-center justify-between flex-wrap bg-green-400 p-6">
        <div class="flex items-center flex-shrink-0 text-white mr-6">
          <px-icon class="mr-2" />
          <router-link
            class="font-semibold text-xl tracking-tight"
            :to="{ name: 'home' }"
          >
            Web Exchange
          </router-link>
        </div>
        <!-- eslint-disable-next-line prettier/prettier -->
        <div class="hidden sm:block w-full block flex-grow lg:flex lg:items-center lg:w-auto">
          <div class="text-sm lg:flex-grow">
            <router-link
              class="block mt-4 lg:inline-block lg:t-0 text-teal-200 hover:text-white mr-4"
              v-for="link in links"
              :key="link.title"
              :to="link.to"
            >
              {{ link.title }}
            </router-link>
          </div>
        </div>
      </nav>
    </nav>
  </header>
</template>

<script>
import PxIcon from '@/components/PxIcon';

export default {
  name: 'PxHeader',
  components: { PxIcon },
  props: {
    links: {
      type: Array,
      default: () => [],
    },
  },
};
</script>
