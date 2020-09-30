<template>
  <div class="row justify-content-center">
    <card-article 
        v-for="(article, index) in articles" 
        @click.native="deleteArticle(index)" 
        :key="index" 
        class="shadow-sm mt-3">
      <h2>{{article.title}}</h2>
      <p class="mt-2">{{article.content}}</p>
    </card-article>
  </div>
</template>

<script>
  import CardArticle from './CardArticle'

  export default {
    props: {
      articles: {
        type: Array,
        required: true
      }
    },
    components: {
      CardArticle
    },
    methods: {
      deleteArticle(index) {
        this.$emit('articleDeleted', index)
      }
    }
  }
</script>

