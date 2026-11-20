<script>
export default {
  props: { modelValue: { type: String, required: true } },
  emits: ["update:modelValue"],
  computed: {
    query: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit("update:modelValue", value);
      },
    },
  },
};
</script>
<template>
  <label class="filter-label"
    >Поиск проекта<input
      class="filter"
      v-model="query"
      placeholder="Например, Food"
      type="search"
  /></label>
</template>
<style scoped>
.filter-label {
  display: flex;
  flex-direction: column;
  gap: 10px;
  min-width: 260px;
  font-size: 13px;
  color: #aebbb1;
}
</style>
