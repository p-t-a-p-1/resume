<template>
  <nav class="nav">
    <div class="nav__wrap">
      <nuxt-link class="nav__link" to="/" exact-active-class="active">
        <font-awesome-icon icon="home" />
        Home
      </nuxt-link>
      <nuxt-link class="nav__link" to="/experience" exact-active-class="active">
        <font-awesome-icon icon="code-branch" />
        Experience
      </nuxt-link>
      <nuxt-link class="nav__link" to="/works" exact-active-class="active">
        <font-awesome-icon icon="sd-card" />
        Works
      </nuxt-link>
      <nuxt-link class="nav__link" to="/posts" exact-active-class="active">
        <font-awesome-icon icon="sticky-note" />Posts
      </nuxt-link>
      <a href="https://github.com/p-t-a-p-1" target="_blank" class="nav__link">
        <font-awesome-icon :icon="['fab', 'github']" />
        GitHub
      </a>
    </div>
  </nav>
</template>

<style lang="scss">
.nav {
  padding: 30px;
  &__link {
    margin-block-end: 10px;
    padding-block-end: 5px;
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
