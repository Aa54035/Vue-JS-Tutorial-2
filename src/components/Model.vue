<template>
  <div class="backdrop" @click="closeModel">
    <div class="model" :class="{ sale: theme === 'star' }">
      <p>{{ Header }}</p>
      <p>{{ SubHeader }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["Header", "SubHeader", "theme"],
  methods: {
    closeModel() {
      this.$emit("customeClose");dir
    },
  },
};
</script>

<style>
.model {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: wheat;
  border-radius: 20px;
}
.backdrop {
  background: rgba(0, 0, 0, 0.5);

  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
p {
  border: 2px dotted black;
}

.model.sale {
  background: crimson;
  color: white;
}
.model.sale p {
  background: greenyellow;
  color: black;
}
</style>

