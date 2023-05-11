<template>
  <button :class="`btn btn--${variant}`" @click="$emit('button-click')">
    {{ text }}
  </button>
</template>

<script>
export default {
  emits: ["button-click"],
  props: {
    text: { type: String },
    variant: { type: String, default: "primary" },
  },
  data() {
    return {
      isActive: false,
    };
  },
  methods: {
    toggle() {
      if (!this.isActive) {
        this.isActive = true;
      } else {
        this.isActive = false;
      }
    },
  },
};
</script>

<style scoped>
.btn {
  border: 3px solid transparent;
  border-radius: 3px;
  padding: 5px;
  cursor: pointer;
}

.btn--primary {
  border-color: var(--primary-dark);
  background-color: var(--primary);
  color: #fff;
}

.btn--primary:hover {
  border-color: var(--primary);
  background-color: var(--primary-dark);
}

.btn--secondary {
  border-color: var(--primary);
  background-color: transparent;
  color: var(--primary);
}

.btn--secondary:hover {
  background-color: var(--primary);
  color: #fff;
}
</style>
