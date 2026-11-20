<script>
export default { props: { project: { type: Object, required: true } } };
</script>
<template>
  <article class="card">
    <img
      :src="project.imageUrl"
      :alt="'Демонстрационный макет ' + project.title"
    />
    <div class="card-body">
      <span class="tag">{{ project.tag }}</span>
      <h3>{{ project.title }}</h3>
      <p>{{ project.description }}</p>
      <span class="muted">Учебный концепт / 2026</span>
    </div>
  </article>
</template>
<style scoped>
.card {
  height: 100%;
}
</style>
