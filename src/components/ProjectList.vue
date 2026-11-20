<script>
import ProjectCard from "./ProjectCard.vue";
export default {
  components: { ProjectCard },
  props: { projects: { type: Array, required: true } },
};
</script>
<template>
  <div v-if="projects.length" class="grid">
    <ProjectCard
      v-for="project in projects"
      :key="project.id"
      :project="project"
    />
  </div>
  <p v-else class="empty" role="status">
    Проекты не найдены. Попробуйте другой запрос.
  </p>
</template>
<style scoped>
.empty {
  color: #bec8bf;
}
</style>
