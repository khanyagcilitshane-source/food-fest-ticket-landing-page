<template>
  <div
    class="card"
    :class="{ featured: ticket.featured }"
  >
    <span
      v-if="ticket.featured"
      class="badge"
    >
      ⭐ Featured
    </span>

    <h2>{{ticket.icon}}{{ ticket.name }}</h2>

    <p class="price">
      R{{ ticket.price }}
    </p>

    <p>
      {{ ticket.description }}
    </p>

    <ul>
      <li
        v-for="benefit in ticket.benefits"
        :key="benefit"
      >
        ✔ {{ benefit }}
      </li>
    </ul>

    <button @click="favouriteTicket">
      ❤️ Favourite
    </button>
  </div>
</template>

<script setup>
defineProps({
  ticket: Object
})

const emit = defineEmits([
  'favourite'
])

function favouriteTicket() {
  emit('favourite')
}
</script>

<style scoped>
.card {
  background: white;
  padding: 2rem;
  border-radius: 20px;
  box-shadow: 0 5px 20px rgba(0,0,0,.1);
  transition: all .3s ease;
}

.featured {
  border: 3px solid gold;

  transform: scale(1.05);

  box-shadow:
    0 10px 30px rgba(255, 215, 0, 0.4);
}

.badge {
  font-weight: bold;
}

.price {
  font-size: 1.4rem;
  font-weight: bold;
}

button {
  width: 100%;
  padding: 10px;
  border: none;
  background: #ff7b00;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}
</style>