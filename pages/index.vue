<template>
  <main class="container">
    <div class="hero is-info is-medium is-bold">
      <h2 class="">株式会社AWESOME</h2>
    </div>
    <schools/>
  </main>
</template>

<script>
import Schools from "~/components/Schools.vue";
export default {
  head: { title: "加古川市の学校一覧" },
  components: { Schools }
};
</script>

<style>
</style>

