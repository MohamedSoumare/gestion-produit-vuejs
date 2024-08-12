<template>
<div class="container mt-4">

    <h2>Ventes Enregistrées</h2>
      <table class="table table-striped">
        <thead>
          <tr>
            <th>Référence</th>
            <th>Désignation</th>
            <th>Quantité Vendue</th>
            <th>Prix de Vente</th>
            <th>Total</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(sale, index) in sales" :key="index">
            <td>{{ sale.reference }}</td>
            <td>{{ sale.designation }}</td>
            <td>{{ sale.quantity }}</td>
            <td>{{ sale.price }}</td>
            <td>{{ (sale.quantity * sale.price).toFixed(2) }} €</td>
          </tr>
        </tbody>
      </table>
    </div>

</template>
  
<script>

  
</script>
  
