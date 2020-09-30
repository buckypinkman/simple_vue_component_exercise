<template>
    <div class="row justify-content-center">
        <div class="col-lg-5 col-md-7">
            <form>
                <div class="form-group">
                    <label style="font-size: 18px">Add Article</label>
                    <input type="text" class="form-control" v-model="article.title" placeholder="Title">
                    <textarea cols="30" rows="4" class="form-control mb-3 mt-3" v-model="article.content" placeholder="Content"></textarea>
                    <button class="btn btn-primary btn-block" @click.prevent="create">Submit</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                article: {
                    title: '',
                    content: ''
                }
            }
        },
        methods: {
            create() {
                this.$emit('articleCreated', this.article)
                this.article = {}
            }
        }
    }
</script>
