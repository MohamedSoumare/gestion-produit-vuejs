<template>
    <div class="container mt-4">
      <h2>Enregistrer une Vente</h2>
      <form @submit.prevent="submitForm">
        <div class="mb-3">
          <label for="reference" class="form-label">Référence</label>
          <input type="text" class="form-control" id="reference" v-model="reference" required>
          <div class="text-danger" v-if="errors.reference">{{ errors.reference }}</div>
        </div>
        <div class="mb-3">
          <label for="designation" class="form-label">Désignation</label>
          <input type="text" class="form-control" id="designation" v-model="designation" required>
          <div class="text-danger" v-if="errors.designation">{{ errors.designation }}</div>
        </div>
        <div class="mb-3">
          <label for="quantity" class="form-label">Quantité Vendue</label>
          <input type="number" class="form-control" id="quantity" v-model="quantity" required>
          <div class="text-danger" v-if="errors.quantity">{{ errors.quantity }}</div>
        </div>
        <div class="mb-3">
          <label for="price" class="form-label">Prix de Vente</label>
          <input type="number" step="0.01" class="form-control" id="price" v-model="price" required>
          <div class="text-danger" v-if="errors.price">{{ errors.price }}</div>
        </div>
        <button type="submit" class="btn btn-primary">Enregistrer</button>
      </form>
    </div>
  </template>
  
<script setup>
  
</script>
  