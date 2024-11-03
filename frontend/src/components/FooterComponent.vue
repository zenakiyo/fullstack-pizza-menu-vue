<script setup>
const hour = new Date().getHours()
const openHours = 8
const closeHours = 22
const isOpen = hour >= openHours && hour < closeHours
</script>

<template>
  <footer className="footer">
    <div v-if="isOpen" className="order">
      <p>We are open untile {{closeHours}}:00. Come visit us or order online.</p>
      <button className="btn">Order</button>
    </div>
    <p v-else>
      We are happy to welcome you between {{openHours}}:00 and {{closeHours}}:00
    </p>
  </footer>
</template>
