<template>
  <h3>Add new transaction</h3>
  <form @submit.prevent="onSubmit" id="form">
    <div class="form-control">
      <label for="text">Text</label>
      <input
        name="text"
        type="text"
        required
        id="text"
        placeholder="Enter text..."
      />
    </div>
    <div class="form-control">
      <label for="amount"
        >Amount <br />
        (negative - expense, positive - income)</label
      >
      <input
        name="amount"
        type="number"
        step="0.01"
        required
        id="amount"
        placeholder="Enter amount..."
      />
    </div>
    <button class="btn">Add transaction</button>
  </form>
</template>

<script setup>
const emit = defineEmits(["transactionSubmitted"]);

const onSubmit = (e) => {
  const form = new FormData(e.target);

  const text = form.get("text");
  const amount = form.get("amount");

  emit("transactionSubmitted", { text, amount });
};
</script>
