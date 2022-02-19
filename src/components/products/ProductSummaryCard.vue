<template>
    <div class="card">
        <h3>{{ product.name }}</h3>

        <h5 class="price">{{ product.price }}</h5>
        <p class="description">{{ product.description }}</p>
        <p class="text-muted">{{ product.category }}</p>
        <button class="view-product-button" @click="$emit('view-product', product)">View</button>
    </div>
</template>


<script>
    export default{
        props:['product']
    }
</script>

<style scoped>
    .card{
        width: 80%;
        margin:10%;
        padding: 10px;
        border-radius: 5px;
        background-color: white;
        box-shadow: 0 0 5px gray;
    }
    .card:hover{
        background-color: paleturquoise;
    }
    .price{
        color: gray;
    }.description{
        font-size: .85rem;
    }
    .text-muted{
        color: gray;
    }
    .view-product-button{
        padding: 10px;
        background-color: rgb(79, 160, 187);
        border: none;
        color: white;
        font-weight: bold;
        font-size: 1.15rem;
        border-radius: 5px;
        cursor: pointer;
    }

    @media (min-width:500px) {
        .card{
            width: 350px;
            margin: 10px;
        }
    }
</style>