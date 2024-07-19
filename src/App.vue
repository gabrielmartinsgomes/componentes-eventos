<script setup>
import { ref } from 'vue'
import ProductList from './components/ProductList.vue'

const produtos = ref([
  { id: 1, nome: 'Produto A', preco: 'R$ 110,25' },
  { id: 2, nome: 'Produto B', preco: 'R$ 12,45' },
  { id: 3, nome: 'Produto C', preco: 'R$ 123,45' },
  { id: 4, nome: 'Produto D', preco: 'R$ 159,57' }
])

function excluirProduto(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id)
  produtos.value.splice(index, 1)
}
function excluirTodosOsProdutos() {
  produtos.value = []
}
</script>

<template>
  <h1>Meus Produtos</h1>
  <ProductList :produtos="produtos" @excluir="excluirProduto" @excluirTudo="excluirTodosOsProdutos"></ProductList>
</template>

<style scoped></style>
