<template>
  <table class="table table-striped">
    <thead>
      <tr>
        <th>Référence</th>
        <th>Désignation</th>
        <th>Quantité</th>
        <th>Prix</th>
        <th>Total</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(sale, index) in sales" :key="index">
        <td>{{ sale.reference }}</td>
        <td>{{ sale.designation }}</td>
        <td>{{ sale.quantity }}</td>
        <td>{{ sale.price.toFixed(2) }} €</td>
        <td>{{ (sale.quantity * sale.price).toFixed(2) }} mru</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    sales: {
      type: Array,
      required: true
    }
  }
}
</script>