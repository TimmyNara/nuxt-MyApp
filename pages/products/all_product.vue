<template>
  <div>
    <h1>Product page</h1>
    <!-- <ul>
        <li v-for="product in data.products" :key="product.id">
            {{ product.title }}
            {{ product.price }}
        </li>
    </ul> -->
    <div class="product-grid">
        <NuxtLink class="container" :to="`/products/${product.id}`" v-for="product in data.products" :key="product.id">
            <h2>{{ product.title }}</h2>
            <img :src="product.thumbnail" alt="product id">
            <p>{{ product.description }}</p>
            <p class="price">price : ${{ product.price }}</p>
        </NuxtLink>
    </div>
  </div>
</template>

<script setup>

const {data: data} = await useFetch('https://dummyjson.com/products')
console.log('---------');
console.log(data);
console.log('---------');
</script>

<style scoped>
.product-grid{
    display: grid;
    grid-template-columns: repeat(3,1fr);
    gap: 30px;
    padding: 30;
}
.container{
    background: #fff;
    padding: 15px;
    text-decoration: none;
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.12);
    text-align: center;
    color: black;
}
.container:hover{
    background: #d5d5d5
}
.price{
    text-align: left;
    font-size: 18px;
    font-weight: bold;
}

</style>