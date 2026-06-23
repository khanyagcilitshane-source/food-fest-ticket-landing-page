<template>
  <header class="hero">
    <h1>Cape Town Food Fest</h1>

    <p>
      Experience the best food, music and culture in one unforgettable weekend.
    </p>

    <button>Get Tickets</button>

    <h3>❤️ Favourites ({{ favouriteCount }})</h3>
  </header>
</template>

<script setup>
defineProps({
  favouriteCount: Number
})
</script>

<style scoped>

.hero {
  text-align: center;
  padding: 5rem 2rem;

  background: linear-gradient(
    135deg,
    #ff7b00,
    #ffb703
  );

  color: white;
}

.hero h1 {
  font-size: 3rem;
}

.hero p {
  margin: 1rem 0;
  font-size: 1.2rem;
}

.hero button {
  padding: 12px 24px;
  border: none;
  border-radius: 25px;
  cursor: pointer;
}
</style>
        