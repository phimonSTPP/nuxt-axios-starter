<template>
  <section>
    <header>
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/about">About</NuxtLink>
    </header>

    <Nuxt />

    <footer id="footer">
        footer
    </footer>
  </section>
</template>

<script>
export default {}
</script>

<style>
#footer{
    background-color: blueviolet;
    min-height: 200px;
}
</style>