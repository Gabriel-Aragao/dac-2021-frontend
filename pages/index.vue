<template>
  <v-layout>
    <v-col>
      <Carousel />
      <br>
      <v-col class="justify-center">
        <v-layout
          row
          wrap
          align-end
          class="padding-content"
        >
          <Product
            v-for="(product, i) in products"
            :key="i"
            :title="product.title"
            :price="product.price"
            class="margin"
          />
        </v-layout>
      </v-col>
      <br>
      <v-pagination
        v-model="page"
        :length="8"
        :total-visible="7"
        circle
      />
    </v-col>
  </v-layout>
</template>

<script>
import Carousel from '~/components/Carousel'
import Product from '~/components/Product'
export default {
  components: {
    Carousel,
    Product
  },
  data () {
    return {
      products: [
        {
          title: 'book1',
          price: 10.5
        },
        {
          title: 'book3',
          price: 10.5
        },
        {
          title: 'book2',
          price: 10.5
        },
        {
          title: 'book3',
          price: 10.5
        },
        {
          title: 'book2',
          price: 10.5
        },
        {
          title: 'book3',
          price: 10.5
        },
        {
          title: 'book2',
          price: 10.5
        },
        {
          title: 'book3',
          price: 10.5
        },
        {
          title: 'book2',
          price: 10.5
        }
      ],
      page: 1
    }
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
