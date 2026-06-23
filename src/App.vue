<template>
  <div>

    <Header
      :favouriteCount="favouriteCount"
    />

    <main class="ticket-grid">

      <TicketCard
        v-for="ticket in tickets"
        :key="ticket.id"
        :ticket="ticket"
        @favourite="addFavourite(ticket)"
      />

    </main>

  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

import Header from './components/Header.vue'
import TicketCard from './components/TicketCard.vue'

const favourites = ref([])

const tickets = ref([
  {
    id: 1,
    icon: "🥉",
    name: "Bronze",
    price: 150,
    description: 'Basic entry package',
    benefits: [
      'Festival Entry'
    ],
    featured: false
  },

  {
    id: 2,
    icon: "🥈",
    name: "Silver",
    price: 300,
    description: 'Entry plus drink voucher',
    benefits: [
      'Festival Entry',
      'Drink Voucher'
    ],
    featured: false
  },

  {
    id: 3,
    icon: "🥇",
    name: "Gold",
    price: 500,
    description: 'Premium VIP experience',
    benefits: [
      'Festival Entry',
      'Drink Voucher',
      'VIP Lounge Access'
    ],
    featured: true
  }
])

function addFavourite(ticket) {
  favourites.value.push(ticket)
}

const favouriteCount = computed(() => {
  return favourites.value.length
})
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #f7f7f7;
  font-family: Arial, sans-serif;
}

.ticket-grid {
  display: grid;

  grid-template-columns:
    repeat(auto-fit, minmax(280px, 1fr));

  gap: 20px;

  padding: 2rem;
}
</style>
