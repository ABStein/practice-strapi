<template>
  <div>
    <div class="navbar bg-gray-300">
      <Navbar/>
    </div>
    <div class="title">
      <h1>Contact Me</h1>
    </div>
  </div>
</template>

<script>
const Navbar = () => import('~/components/Navbar.vue')

export default {
  components: {
    Navbar
  }
}
</script>
<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: auto auto;
  padding: 10px;
  min-height: 20vh;
  display: flex;
  /* flex-direction: column; */
  justify-content: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-weight: 300;
  text-align: center;
  font-size: 50px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
