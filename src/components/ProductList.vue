<script setup>
defineProps(['produtos'])
</script>
<template>
  <table>
    <thead>
      <tr>
        <th>ID</th>
        <th>Nome</th>
        <th>Preço</th>
        <th>Ações</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="produto in produtos" :key="produto.id">
        <td>{{ produto.id }}</td>
        <td>{{ produto.nome }}</td>
        <td>{{ produto.preco }}</td>
        <td><i class="mdi mdi-delete" @click="$emit('excluir', produto.id)" /></td>
      </tr>
    </tbody>
  </table>
  <button @click="$emit('excluirTudo')">Excluir Tudo</button>
</template>
