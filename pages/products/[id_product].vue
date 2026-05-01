<template>
    <div class="page">
        <!-- <head> -->
            <!-- <title>My app | {{ id_product.title }}</title> -->
            <!-- <meta name="description" :content="id_product.description"> -->
        <!-- </head> -->
        <NuxtLink to="/products/all_product" class="back-btn"> back to products</NuxtLink>
        <div class="card">
            <img :src="product.thumbnail" alt="product image" class="product-image">
            <div class="info">
                <h1 class="product-title">{{ product.title }}</h1>
                <span class="category">{{ product.category }}</span>
                <p class="description">{{ product.description }}</p>
                <div class="price">${{product.price }}</div>
            </div>
        </div>
    </div>
</template>

<script setup>
const route = useRoute()
let id_product = route.params.id_product

const {data: product} = await useFetch(`https://dummyjson.com/products/${id_product}`)
console.log(product);

</script>

<style>
.page{
    max-width: 900px;
    margin: 40px auto;
    padding: 0 20px;
    font-family: sans-serif;
}
.back-btn{
    display: inline-block;
    margin-bottom: 24px;
    color: #555;
    text-decoration: none;
    font-size: 0.95em;
}

.back-btn:hover{
    color: #000;
}

.card{
    display: flex;
    gap: 40px;
    background: #fff;
    box-shadow: 0 2px 20px rgba(0,0,0,0.1);
    padding: 30px;
    border-radius: 12px;
}

.product-img{
    width: 280px;
    height: 280px;
    object-fit: contain;
    border-radius: 8px;
    background: #f5f5f5f5;
    flex-shrink: 0;
}
.info{
    display: flex;
    flex-direction: column;
    gap: 12px;
}
.product-title{
    font-size: 1.6em;
    font-weight: 700;
    color: #222;
    margin: 0;
}
.category{
    display: inline-block;
    background: #ffe0a0;
    color: #b06000;
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 0.85em;
    font-weight: 600;
    text-transform: capitalize;
}

.description{
    color: #555;
    line-height: 1.6;
    margin: 0;
}

.price{
    font-size: 1.8em;
    font-weight: 700;
    color: #e67e22;
}
</style>