<template>
  <section class="project-meta">
    <h2 class="project-title">{{ title }}</h2>
    <ul class="project-categories">
      <li
        class="project-category"
        v-for="(category, index) in categories"
        :key="index"
      >
        {{ category }}
      </li>
    </ul>

  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: false
    },
    categories: {
      type: Array,
      required: false
    }
  }
};
</script>

<style lang="scss" scoped>
.project-meta {
  text-align: center;
  padding: .5rem 0;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  line-height: 1.5;
/*  border-bottom: 2px dotted #555; */
  margin-bottom: 4em;
}
.project-title {
  flex: 0 0 40%;
  font-size: 1.5rem;
  font-weight: 300;
  margin: 0;
  font-family: 'Josefin Sans', serif;
  color: lightcoral;
}
.project-categories {
  flex: 1;
  padding: 0;
  margin: 0;
  list-style: none;
  display: none;
}
.project-category {
  padding: 0;
  margin: 0;
  display: none;
}
.project-year {
  flex: 1;
  text-align: right;
  font-style: italic;
  color: rgba(255,255,255,.2);
}
</style>
