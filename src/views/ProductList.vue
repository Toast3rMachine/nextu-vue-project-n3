<script lang="ts">
interface Product {
  id: number
  label: string
  description: string
  quantity: number
}

defineProps<{ products: Product[] }>()

const getStatus = (quantity: number): String => {
  return quantity > 0 ? 'Disponible' : 'Indisponible'
}
</script>

<template>
  <table>
    <thead>
      <tr>
        <th>ID</th>
        <th>Label</th>
        <th>Description</th>
        <th>Statut</th>
      </tr>
    </thead>
    <body>
      <tr v-for="product in products" :key="product.id">
        <td>{{ product.id }}</td>
        <td>{{ product.label }}</td>
        <td>{{ product.description }}</td>
        <td>{{ getStatus(product.quantity) }}</td>
      </tr>
    </body>
  </table>
</template>
