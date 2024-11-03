<script setup>
import { ref } from 'vue'

import HeaderComponent from './components/HeaderComponent.vue'
import PizzaComponent from './components/PizzaComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
const data = ref('')
</script>

<template>
  <div className="container">
    <HeaderComponent />
    <main className="menu">
      <h2>Our Menu</h2>
      <Div v-if="data.length > 0">
        <p>
          Authentic Intalian cuisin. {data.length} creative dishes to choose
          from. All form out stone over, all organic all delicious.
        </p>
        <ul className="pizzas">
          {data.map(pizza =>
          <PizzaComponent key="{pizza.name}" {...pizza} />)}
        </ul>
      </Div>
      <p v-else>We are still working on our menu. Please come back later 🙂</p>
    </main>

    <FooterComponent />
  </div>
</template>

<style scoped></style>
