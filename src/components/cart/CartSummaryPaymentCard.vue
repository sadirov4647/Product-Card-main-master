<template>
    <div class="cart-tem-card">
        <h3>Cart Total: {{ cart_total.toFixed(2) }}</h3>
    </div>
</template>

<script>
    export default{
        computed:{
            cart_total(){
                return this.$store.getters.cartTotal
            }
        }
    }
</script>