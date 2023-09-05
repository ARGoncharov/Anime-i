<template lang="pug">
  .page.index
    .content
      .header
        h1.title anime-i
      form.search-box
        input.search-field(type="search" placeholder="Search for anime..." required)
</template>

<script>
export default {
  name: 'MainComponent',
  data () {
    return {
    }
  },
  methods: {
    changeTitle () {
      const title = document.querySelector('.title')
      title.style.fontSize = '120px'
      title.style.color = 'deeppink'
      title.style.transition = '0.5s'
    }
  },
  mounted () {
    const searchField = document.querySelector('.search-field')
    searchField.addEventListener('focus', this.changeTitle)
  },
  beforeDestroy () {
    const searchField = document.querySelector('.search-field')
    searchField.removeEventListener('focus', this.changeTitle)
  }
}
</script>

<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@700&family=Oswald:wght@300&display=swap');

.page.index {
  .content {
    .header {
      .title {
        font-family: Orbitron, sans-serif;
        font-size: 60px;
        text-align: center;
        padding-top: 60px;
        padding-bottom: 60px;
      }
    }
    .search-box {
      display: flex;
      justify-content: center;
      padding-left: 30px;
      padding-right: 30px;

      .search-field {
        appearance: none;
        border: none;
        outline: none;
        background-color: gainsboro;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
        display: block;
        width: 100%;
        max-width: 600px;
        padding: 15px;
        border-radius: 10px;
        font-size: 20px;
        &::placeholder {
          color: black;
        }
        &:focus,
        &:valid
        {
          background-color: black;
          color: gainsboro;
        }
      }
    }
  }
}

</style>
