<template>
    <form class="" action="#" method="post">
      <input
        v-model="bookTitle"
        type="text"
        name="title"
        value=""
        placeholder="Book Title"
      >
      <input
        v-model="bookAuthor"
        type="text"
        name="author"
        value=""
        placeholder="Book author"
      >
      <button
        type="submit"
        name="button"
        @submit.prevent="bookSubmit(bookTitle, bookAuthor)"
      >Add Book</button>
    </form>
</template>

<script>
    export default {
        name: "BookForm",
        props: ['books'],
        data () {
            return {
              bookTitle: '',
              bookAuthor: '',
            }
        },
      methods: {
          bookSubmit(bookTitle, bookAuthor) {
            this.$emit('addBook', bookTitle, bookAuthor);
          }
      }
    }
</script>

<style scoped>

</style>
