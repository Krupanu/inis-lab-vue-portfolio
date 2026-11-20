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
  border: 1px solid #354039;
  border-radius: 12px;
  overflow: hidden;
  background: #19201c;
}

.card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  display: block;
}

.card-body {
  padding: 24px;
}

.card h3 {
  font-size: 24px;
  margin: 12px 0;
}

.card p {
  color: #b9c4bc;
  line-height: 1.65;
  min-height: 52px;
}

.card a {
  font-size: 14px;
  text-decoration: underline;
  text-underline-offset: 4px;
}

  .card img {
    height: 190px;
  }
.card {
  height: 100%;
}
</style>
