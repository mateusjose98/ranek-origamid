<template>
<section class="produtos-container">
    <div v-for="produto in produtos" :key="produto.id">
        <img v-if="produto.fotos" :src="produto.fotos[0]" alt="foto" />
        <p class="preco">{{produto.preco}}</p>
        <h2 class="titulo">{{produto.nome}}</h2>
        <p class="">{{produto.descricao}}</p>
        
        
    </div>
</section>
</template>

<script>
export default {
    data() {
        return {
            produtos: null
        }
    },
    created() {
        this.getProdutos();
    },
    methods: {
        getProdutos() {
            fetch('http://localhost:3000/produto').then((r) => r.json()).then(j => {
                this.produtos = j
            })
        }
    }
};
</script>

<style>
</style>
