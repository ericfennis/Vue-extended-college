<template>
   <main>
        <section id="results">
            <h3>Bier&#127866;</h3>
           <div class="container">

              <div class="product col-md-3 col-sm-6" v-for="product in products">
               <div class="product-body thumbnail">
                  <div class="product-name caption">{{ product.name }}</div>
                  <div class="product-price">&euro;{{ product.price }}</div>
               </div>
            </div>
           </div>
        </section>
</main>
</template>

<script>
    export default {
      data() {
         return {
            products: [],
         }
      },
        mounted() {
            console.log('Component mounted.')
        },
        created() {
          this.getProducts();
        },
        methods: {
           getProducts() {
            axios.get('/api/products').then(response => this.products = response.data);
          }
        }
    }
</script>
