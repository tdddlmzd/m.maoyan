<template>
  <div>
    <ul>
      <nuxt-link to="/film/nowingplay" tag="li" activeClass="active">film</nuxt-link>
      <nuxt-link to="/center" tag="li" activeClass="active">center</nuxt-link>
      <nuxt-link to="/cinema" tag="li" activeClass="active">cinema</nuxt-link>
    </ul>
    <nuxt/>
  </div>
</template>

<style>
ul {
  list-style: none;
}
.active {
  color: red;
}
</style>
