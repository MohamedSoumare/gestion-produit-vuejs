<template>
  <div class="container">
    <h1 class="mb-4">Enregistrement des ventes</h1>
    
    <form @submit.prevent="submitSale" class="mb-4">

      <div class="mb-3">
        <label for="reference" class="form-label">Référence</label>
        <input v-model="sale.reference" type="text" class="form-control" id="reference" required>
        <div v-if="errors.reference" class="text-danger">{{ errors.reference }}</div>
      </div>
      
      <div class="mb-3">
        <label for="designation" class="form-label">Désignation</label>
        <input v-model="sale.designation" type="text" class="form-control" id="designation" required>
        <div v-if="errors.designation" class="text-danger">{{ errors.designation }}</div>
      </div>
      
      <div class="mb-3">
        <label for="quantity" class="form-label">Quantité</label>
        <input v-model.number="sale.quantity" type="number" class="form-control" id="quantity" required min="1">
        <div v-if="errors.quantity" class="text-danger">{{ errors.quantity }}</div>
      </div>
      
      <div class="mb-3">
        <label for="price" class="form-label">Prix de vente</label>
        <input v-model.number="sale.price" type="number" class="form-control" id="price" required min="0" step="0.01">
        <div v-if="errors.price" class="text-danger">{{ errors.price }}</div>
      </div>
      
      <button type="submit" class="btn btn-primary">Enregistrer la vente</button>
    </form>
    
    <Produits :sales="sales" />

  </div>
</template>

<script>
import { ref, reactive } from 'vue'
// import Produits from './Produits.vue'
import Produits from './Produits.vue';

export default {
  components: {
    Produits
  },
  setup() {
    const sale = reactive({
      reference: '',
      designation: '',
      quantity: 1,
      price: 0
    })

    const sales = ref([])
    const errors = reactive({})

    const validateSale = () => {
      errors.reference = sale.reference.trim() === '' ? 'La référence est requise' : ''
      errors.designation = sale.designation.trim() === '' ? 'La désignation est requise' : ''
      errors.quantity = sale.quantity < 1 ? 'La quantité doit être supérieure à 0' : ''
      errors.price = sale.price <= 0 ? 'Le prix doit être supérieur à 0' : ''

      return Object.values(errors).every(error => error === '')
    }

    const submitSale = () => {
      if (validateSale()) {
        sales.value.push({ ...sale })
        Object.assign(sale, { reference: '', designation: '', quantity: 1, price: 0 })
      }
    }

    return {
      sale,
      sales,
      errors,
      submitSale
    }
  }
}
</script>