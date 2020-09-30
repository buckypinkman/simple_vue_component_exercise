<template>
  <div>
    <navbar/>
    <div class="container mt-4">
      <app-add-article @articleCreated="createArticle"/>
      <hr style="width: 85%">
      <app-article :articles="articles" @articleDeleted="deleteArticle"/>
      <div class="row mt-3">
        <div class="col">
          <p class="text-center">&copy;2020 Rangga Dimas</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Article from './components/Article'
  import AddArticle from './components/AddArticle'
  import Navbar from './components/Navbar'

  export default {
    data() {
      return {
        articles: [
          {
            title: 'Hello World',
            content: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laborum minus, enim dicta officiis nesciunt a, sint facilis alias possimus impedit necessitatibus recusandae tempore mollitia ut totam quos omnis, aliquam dolores.'
          }
        ]
      }
    },
    methods: {
      createArticle(article) {
        (article.title.textContent == '' || article.content.texContent == '') ? false : 
        this.articles.unshift(article)
      },
      deleteArticle(index) {
        this.articles.splice(index,1)
      }
    },
    components: {
      appArticle: Article,
      appAddArticle: AddArticle,
      navbar: Navbar
    }
  }
</script>

<style>
  body {
    background-color: rgb(244, 246, 255);
  }
</style>
