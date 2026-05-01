<template>
    <div>      
        <header>
            <nav>
                <h1 class="logo">My-app</h1>
                <NuxtLink to="/">Home</NuxtLink>
                <NuxtLink to="/about">about</NuxtLink>
                <NuxtLink to="/products/all_product">All product</NuxtLink>
            </nav>
        </header>
        <div>
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
nav{
    display: flex;
    gap: 20px;
    justify-content: center;
    align-items: center;
    background: #7a7a7a;
    
}
nav a{
    color: white;
    text-decoration: none;
    font-size: 20px;
    margin-left: 12px;
    padding: 5px;
}
nav a:hover{
    color: aquamarine;
}
.logo{
    color: white;
    font-size: 24px;
    font-weight: bold;
    margin-right: auto;
    margin-left: 15px;
}
</style>