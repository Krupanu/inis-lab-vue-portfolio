<script>
import ProjectList from "./components/ProjectList.vue";
import FilterInput from "./components/FilterInput.vue";
import { projects } from "./data";
export default {
  components: { ProjectList, FilterInput },
  data() {
    return { projects, query: "" };
  },
  computed: {
    filteredProjects() {
      const q = this.query.trim().toLocaleLowerCase();
      return this.projects.filter((p) =>
        (p.title + " " + p.description).toLocaleLowerCase().includes(q),
      );
    },
  },
};
</script>
<template>
  <header>
    <a class="logo" href="#home"
      ><img src="/assets/logo.svg" alt="Монограмма М" />АЛЕКСЕЙ / DEV</a
    >
    <nav aria-label="Основная навигация">
      <a href="#projects">Проекты</a><a href="#about">Обо мне</a
      ><a href="#contact">Контакт</a>
    </nav>
  </header>
  <main>
    <section id="home" class="hero">
      <span class="eyebrow">ПОРТФОЛИО / 2026</span>
      <h1>Создаю интерфейсы.<br /><em>Продумываю детали.</em></h1>
      <p class="intro">
        Я Алексей Максимович, студент БГУИР. Изучаю веб-разработку и превращаю
        идеи в понятные цифровые продукты.
      </p>
      <div class="actions">
        <a class="btn" href="#projects"
          >Смотреть проекты <span aria-hidden="true">↗</span></a
        ><a class="btn secondary" href="#contact">Связаться</a>
      </div>
    </section>
    <section id="projects">
      <div class="section-head">
        <div>
          <h2>Избранные проекты</h2>
          <p class="count">
            Найдено: {{ filteredProjects.length }} из {{ projects.length }}
          </p>
        </div>
        <FilterInput v-model="query" />
      </div>
      <ProjectList :projects="filteredProjects" />
    </section>
    <section class="about" id="about">
      <span class="eyebrow">01 / ОБО МНЕ</span>
      <div class="about-wrap">
        <img
          class="portrait"
          src="/assets/avatar.webp"
          alt="Условный аватар разработчика"
        />
        <div>
          <h2>От структуры — к деталям</h2>
          <p>
            Учусь на факультете компьютерного проектирования БГУИР. Практикую
            компонентный подход, адаптивную вёрстку и работу с данными. Здесь
            собраны демонстрационные интерфейсы учебных проектов.
          </p>
        </div>
      </div>
    </section>
    <section class="contact" id="contact">
      <h2>Открыт к новым идеям</h2>
      <p class="intro">Мои учебные проекты и контакты — на GitHub.</p>
      <a class="btn" href="https://github.com/Krupanu">Открыть GitHub ↗</a>
    </section>
  </main>
  <footer>
    <span>© 2026 Алексей Максимович</span
    ><a href="https://github.com/Krupanu">GitHub / Krupanu ↗</a>
  </footer>
</template>
<style scoped>
main {
  min-height: 80vh;
}
</style>
