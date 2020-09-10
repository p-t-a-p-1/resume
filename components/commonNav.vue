<template>
  <nav class="nav">
    <div class="nav__wrap">
      <nuxt-link class="nav__link" to="/">Home</nuxt-link>
      <nuxt-link class="nav__link" to="/experience">Experience</nuxt-link>
      <nuxt-link class="nav__link" to="/works">Works</nuxt-link>
      <nuxt-link class="nav__link" to="/posts">Posts</nuxt-link>
      <a href="https://github.com/p-t-a-p-1" target="_blank" class="nav__link">
        GitHub
      </a>
    </div>
  </nav>
</template>

<style lang="scss">
.nav {
  padding: 30px;
  &__link {
    margin-bottom: 10px;
    display: block;
    font-weight: bold;
    color: #fff;
    text-align: left;
    text-decoration: none;
    border-bottom: 1px solid #fff;
    &.active {
      color: #000;
      border-bottom: 1px solid #000;
    }
    svg {
      width: 20px !important;
      margin-right: 10px;
    }
    &:hover {
      opacity: 0.7;
    }
  }
}
</style>
