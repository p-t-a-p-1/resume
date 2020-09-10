<template>
  <div class="home">
    <dl class="profile">
      <div class="profile__box">
        <dt class="profile__key">Name.</dt>
        <dd class="profile__value">Hakozaki</dd>
      </div>
      <div class="profile__box">
        <dt class="profile__key">Age.</dt>
        <dd class="profile__value">{{ age }}</dd>
      </div>
      <div class="profile__box">
        <dt class="profile__key">Birth Day.</dt>
        <dd class="profile__value">{{ birthday }}</dd>
      </div>
      <div class="profile__box">
        <dt class="profile__key">Location.</dt>
        <dd class="profile__value">Sapporo</dd>
      </div>
    </dl>
    <div class="github">
      <a href="https://github.com/p-t-a-p-1" target="_blank">
        <img
          src="https://grass-graph.moshimo.works/images/p-t-a-p-1.png?background=none"
        />
      </a>
    </div>
  </div>
</template>

<style lang="scss">
.profile {
  &__box {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    font-size: 1.5em;
  }
  &__key {
    width: 150px;
  }
  &__value {
    margin: 0;
  }
}
.github {
  margin-top: 100px;
  a {
    &:hover {
      opacity: 0.7;
    }
  }
}
</style>

<script>
export default {
  name: 'Home',
  data() {
    return {
      age: '',
      birthday: '1996-02-25',
    }
  },
  created() {
    const birthSplit = this.birthday.split('-')
    const birthYear = parseInt(birthSplit[0])
    const birthMonth = parseInt(birthSplit[1])
    const birthDay = parseInt(birthSplit[2])
    this.age = this.calcAge(birthYear, birthMonth, birthDay)
  },
  methods: {
    // 年齢計算
    calcAge(year, month, day) {
      const birthDate = year * 10000 + month * 100 + day
      const today = new Date()
      const targetDate =
        today.getFullYear() * 10000 +
        (today.getMonth() + 1) * 100 +
        today.getDate()
      const resultAge = Math.floor((targetDate - birthDate) / 10000)
      return resultAge
    },
  },
}
</script>
