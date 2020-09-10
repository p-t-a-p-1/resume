<template>
  <div class="posts">
    <div class="posts-wrap">
      <magic-grid class="posts-list">
        <div
          v-for="(post, index) in posts_qiita"
          :key="index"
          class="posts-item media"
        >
          <a :href="post.url" target="_blank">
            <span class="media__title">{{ post.title }}</span>
            <div class="media__tags">
              <font-awesome-icon icon="tag" />
              <ul class="tag-list">
                <li
                  v-for="tag in post.tags"
                  :key="tag.name"
                  class="media__tag tag-item"
                >
                  {{ tag.name }}
                </li>
              </ul>
            </div>
            <ul class="count-list">
              <li class="count-likes">
                <span>{{ post.likes_count }}</span>
                LGTM
              </li>
            </ul>
          </a>
        </div>
      </magic-grid>
    </div>
    <!-- <pre>{{posts_qiita}}</pre> -->
  </div>
</template>

<style lang="scss">
.media {
  border: 1px solid #2c3e50;
  padding: 20px;
  box-sizing: border-box;
  min-width: 280px;
  border-radius: 13px;
  &:hover {
    cursor: pointer;
    opacity: 0.7;
  }
  a {
    color: #2c3e50;
    text-decoration: none;
  }
  &__tags {
    display: flex;
    align-items: center;
  }
}
.tag-list {
  margin: 0;
  margin-left: 10px;
  padding: 0;
  list-style-type: none;
}
.tag-item {
  display: inline-block;
  list-style-type: none;
  &:not(:last-of-type):after {
    content: ',';
    margin-right: 3px;
  }
}
.count-list {
  display: block;
  margin: 0;
}
.count-likes {
  span {
    font-size: 1.2em;
    margin-right: 5px;
  }
}
</style>

<script>
export default {
  name: 'Posts',
  data() {
    return {
      posts_qiita: [],
    }
  },
  async created() {
    try {
      await this.$axios
        .get('https://qiita.com/api/v2/users/p-t-a-p-1/items')
        .then((response) => {
          this.posts_qiita = response.data
        })
    } catch (e) {
      // console.error(e)
    }
  },
}
</script>
