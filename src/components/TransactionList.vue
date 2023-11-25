<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li class="minus" v-for="transaction in transactions" :key="transaction.id">
      Cash <span>-{{ transaction.amount }}</span><button class="delete-btn">x</button>
    </li>

  </ul>
</template>

<script>
export default {
  data() {
    return {
      transactions: [
        { id: 1, text: "Flower", amount: -19.99 },
        { id: 1, text: "Flower", amount: 19.99 },
        { id: 1, text: "Flower", amount: 39.99 },
        { id: 1, text: "Flower", amount: -19.99 },
        { id: 1, text: "Flower", amount: -19.99 },
      ],
    };
  },
};
</script>
