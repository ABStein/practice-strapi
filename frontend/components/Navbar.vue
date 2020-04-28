<template>
  <header class="sm:flex sm:justify-between sm:px-4 sm:py-3">
    <div class="flex items-center justify-between sm:items-center px-4 py-3 sm:p-0">
      <div class="home-logo">
        <a href="/"><img class="h-8" src="../img/logo5.png" alt="Fusion" ></a>
      </div>
      <div class="nav-menu sm:hidden">
        <button type="button" class="block text-gray-200 hover:text-white focus:text-white focus:outline-none" @click="isOpen = !isOpen">
          <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
            <path v-if="isOpen" fill-rule="evenodd" d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z" />
            <path v-if="!isOpen" fill-rule="evenodd" d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z" />
          </svg>
        </button>
      </div>
    </div>

    <div :class="isOpen ? 'block' : 'hidden'" class="px-2 pt-2 pb-4 sm:flex">
      <a href="/" class="block px-2 py-1 text-gray font-semibold rounded hover:bg-gray-500">Home</a>
      <a href="/about" class="mt-1 block px-2 py-1 text-gray font-semibold rounded hover:bg-gray-500 sm:mt-0 sm:ml-2">About</a>
      <a href="/contact" class="mt-1 block px-2 py-1 text-gray font-semibold rounded hover:bg-gray-500 sm:mt-0 sm:ml-2">Contact</a>
    </div>
  </header>
</template>

<script>
export default {
  data () {
    return {
      isOpen: false
    }
  }
}
</script>
