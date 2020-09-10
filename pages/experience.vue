<template>
  <div class="experience">
    <div class="experience__wrap languages">
      <h2 class="experience__title">Languages</h2>
      <magic-grid class="experience__list">
        <div v-for="(lang, key) in lang_list" :key="key" class="card">
          <img :src="lang.icon" width="100" height="100" :alt="lang.name" />
          <p class="card__detail mask">
            {{ lang.name }}<br />{{ lang.year }}<br />{{ lang.note }}
          </p>
        </div>
      </magic-grid>
    </div>

    <div class="experience__wrap tools">
      <h2 class="experience__title">Tools</h2>
      <magic-grid class="experience__list">
        <div v-for="(tool, key) in tool_list" :key="key" class="card">
          <img :src="tool.icon" width="100" height="100" :alt="tool.name" />
          <p class="card__detail mask">
            {{ tool.name }}<br />{{ tool.year }}<br />{{ tool.note }}
          </p>
        </div>
      </magic-grid>
    </div>

    <div class="experience__wrap other">
      <h2 class="experience__title">Other</h2>
      <magic-grid class="experience__list">
        <div v-for="(other, key) in other_list" :key="key" class="card">
          <img :src="other.icon" width="100" height="100" :alt="other.name" />
          <p class="card__detail mask">
            {{ other.name }}<br />{{ other.year }}<br />{{ other.note }}
          </p>
        </div>
      </magic-grid>
    </div>
  </div>
</template>

<style lang="scss">
.experience {
  &__wrap {
    & + .experience__wrap {
      margin-block-start: 50px;
    }
  }
  &__title {
    margin-block-end: 30px;
    text-align: center;
  }
}
ul {
  padding: 0;
}
.card {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 200px;
  height: 200px;
  text-align: center;
  transition: 0.2s ease-in-out;
  border: 1px solid #666;
  border-radius: 13px;
  box-shadow: 0px 10px 30px -5px rgba(0, 0, 0, 0.1);
  position: relative;
  &:hover {
    box-shadow: 0px 30px 45px -15px rgba(0, 0, 0, 0.8);
    .mask {
      opacity: 1;
    }
  }
  &__detail {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 15px;
    box-sizing: border-box;
    color: #fff;
    font-weight: bold;
    font-size: 1.2em;
  }
}
// hover時のテキスト
.mask {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  margin: auto;
  opacity: 0;
  background-color: rgba(0, 0, 0, 0.6);
  border-radius: 13px;
  transition: all 0.2s ease;
  -webkit-transition: all 0.2s ease;
}
</style>

<script>
import Vue from 'vue'
import MagicGrid from 'vue-magic-grid'
export default {
  name: 'Experience',
  data() {
    return {
      lang_list: [
        {
          name: 'HTML',
          year: '3年',
          note: '',
          icon: require('../assets/logo/html5-brands.svg'),
        },
        {
          name: 'CSS',
          year: '3年',
          note: '好きなCSS設計はBEMです！',
          icon: require('../assets/logo/css3-alt-brands.svg'),
        },
        {
          name: 'JavaScript',
          year: '3年',
          note: 'jQuery',
          icon: require('../assets/logo/js-square-brands.svg'),
        },
        {
          name: 'WordPress',
          year: '3年',
          note: '',
          icon: require('../assets/logo/wordpress-brands.svg'),
        },
        {
          name: 'PHP',
          year: '1.5年',
          note: '',
          icon: require('../assets/logo/php-brands.svg'),
        },
        {
          name: 'Sass',
          year: '1年',
          note: '',
          icon: require('../assets/logo/sass-brands.svg'),
        },
        {
          name: 'Node.js',
          year: '3ヶ月',
          note: 'Express',
          icon: require('../assets/logo/node-js-brands.svg'),
        },
        {
          name: 'Vue.js',
          year: '3ヶ月',
          note: 'このポートフォリオぐらいです..',
          icon: require('../assets/logo/vuejs-brands.svg'),
        },
        {
          name: 'Python',
          year: '3ヶ月',
          note: 'FastAPI',
          icon: require('../assets/logo/python-brands.svg'),
        },
        {
          name: 'SQL',
          year: '3ヶ月',
          note: '',
          icon: require('../assets/logo/database-solid.svg'),
        },
      ],
      tool_list: [
        {
          name: 'Git',
          year: '3年',
          note: 'GitLabCIは少し',
          icon: require('../assets/logo/git-brands.svg'),
        },
        {
          name: 'Docker',
          year: '3ヶ月',
          note: '',
          icon: require('../assets/logo/docker-brands.svg'),
        },
        {
          name: 'Illustrator',
          year: '少し',
          note: '',
          icon: require('../assets/logo/adobe-brands.svg'),
        },
      ],
      other_list: [
        {
          name: 'Slack',
          year: '3年',
          note: '',
          icon: require('../assets/logo/slack-brands.svg'),
        },
        {
          name: 'Discord',
          year: '1年',
          note: '',
          icon: require('../assets/logo/discord-brands.svg'),
        },
        {
          name: 'Skype',
          year: '3年',
          note: '',
          icon: require('../assets/logo/skype-brands.svg'),
        },
      ],
    }
  },
}
Vue.use(MagicGrid)
</script>
