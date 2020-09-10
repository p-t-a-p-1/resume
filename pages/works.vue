<template>
  <div class="works">
    <div class="works-wrap">
      <magic-grid class="works-list">
        <div
          v-for="(work, index) in work_list"
          :key="index"
          class="works-item work"
        >
          <p class="work__title">{{ work.title }}</p>
          <img :src="work.img" width="100%" :alt="work.title" />
          <p>
            <a
              v-if="work.url !== ''"
              :href="work.url"
              target="_blank"
              class="work__url"
            >
              [URL]
            </a>
            <a :href="work.github" target="_blank" class="work__git">
              [GitHub]
            </a>
          </p>
        </div>
      </magic-grid>
    </div>
  </div>
</template>

<style lang="scss">
.work {
  border: 1px solid #2c3e50;
  padding: 20px;
  box-sizing: border-box;
  border-radius: 13px;
  max-width: 100%;
  &:hover {
  }
  &__title {
    text-align: center;
  }
  &__url {
    &::after {
      content: ',';
    }
  }
}
</style>

<script>
export default {
  name: 'Works',
  data() {
    return {
      work_list: [
        {
          title: '自動ニュース追加サイト',
          note: '',
          lang: 'Node.js(Express)',
          url: 'https://japan-today.net/',
          github: 'https://github.com/p-t-a-p-1/japan-auto-news',
          img: require('../assets/works/japan-today-news.png'),
        },
        {
          title: 'ポーカー',
          note: '',
          lang: 'Python',
          url: '',
          github: 'https://github.com/p-t-a-p-1/poker',
          img: require('../assets/works/poker.png'),
        },
        {
          title: 'ブラックジャック',
          note: '',
          lang: 'Python',
          url: '',
          github: 'https://github.com/p-t-a-p-1/bj_2.0',
          img: require('../assets/works/bj.png'),
        },
        {
          title: 'TODOアプリ',
          note: '',
          lang: 'Python(FastAPI)',
          url: '',
          github: 'https://github.com/p-t-a-p-1/fastapi-todo-app',
          img: require('../assets/works/todoapp_fastapi.png'),
        },
      ],
    }
  },
}
</script>
