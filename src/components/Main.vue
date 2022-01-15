<template>
  <main>
    <div class="row">
      <div class="col-md-6 col-md-offset-2 description">
        <h1 v-text="product.title"></h1>
        <p v-html="product.description"></p>
        <p class="price">
          {{product.price | formatPrice}}
        </p>
      </div>
    </div>
  </main>
</template>
<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      product: {
        id: 1001,
        title: "Cat Food, 25lb bag",
        description: "A 25 pound bag of <em>irresistible</em>," + " organic goodness for your cat.",
        price: 2000,
        image: "assets/images/product-fullsize.png",
      }
    }
  },
  filters: {
    formatPrice(price) {	//#B
      if (!parseInt(price)) { return ""; }	//#C
      if (price > 99999) {	//#D
        var priceString = (price / 100).toFixed(2);	//#E
        var priceArray = priceString.split("").reverse();	//#F
        var index = 3;	//#F
        while (priceArray.length > index + 3) {	//#F
          priceArray.splice(index + 3, 0, ",");	//#F
          index += 4;	//#F
        }	//#F
        return "$" + priceArray.reverse().join("");	//#G
      } else {
        return "$" + (price / 100).toFixed(2);	//#H
      }
    }

  },
}
</script>
<style scoped>

</style>
