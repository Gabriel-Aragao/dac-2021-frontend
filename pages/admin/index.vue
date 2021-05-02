<template>
  <Admin>
    <v-layout>
      <v-col>
        <v-col class="justify-center">
          <v-layout
            row
            wrap
            align-end
            class="padding-content"
          >
            <BookSave />
          </v-layout>
        </v-col>
        <br>
        <v-pagination
          v-model="page"
          :length="4"
          circle
        />
      </v-col>
    </v-layout>
  </Admin>
</template>

<script>
import Admin from '~/layouts/admin.vue'
import BookSave from '~/components/BookSave'
export default {
  components: {
    BookSave
  },
  data () {
    return {
      title: '',
      subtitle: '',
      description: '',
      isbn: '',
      year: 0,
      price: 0,
      stock: 0,
      page: 1
    }
  },
  template: {
    Admin
  }
}
</script>
<style scoped>
  .justify-center{
    justify-content: center;
  }
  .padding-content{
    justify-content: space-between;
    align-content: space-around;
  }
  .margin{
    margin: 10px 0;
  }
</style>
