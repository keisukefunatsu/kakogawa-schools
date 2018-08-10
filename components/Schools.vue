<template>
	<div class="container">
    <nav class="panel">
      <p class="panel-heading">
        加古川市の学校
      </p>
      <p class="panel-tabs">
        <a @click="switchSchool('')" class="">all</a>
        <a @click="switchSchool('小学')">小学校</a>
        <a @click="switchSchool('中学')">中学校</a>
        <a @click="switchSchool('養護')">養護学校</a>
      </p>
      <div v-for="(school, index) in sortedSchools" v-bind:key="index">
        <nuxt-link :to="`/school/${school.学校名}`" class="panel-block">
          <span class="panel-icon">
            <i class="fas fa-book" aria-hidden="true"></i>
          </span>
              {{school.学校名}}
        </nuxt-link>
      </div>
    </nav>
    </div>
</template>


<script>
import schools from "~/stu_29_latlng.json";
export default {
  name: "schools",
  data() {
    return {
      isActive: true,

      schools,
      sortedSchools: schools,
      type: ""
    };
  },
  methods: {
    switchSchool(type) {
      this.sortedSchools = schools.filter(e => {
        return e["学校名"].includes(type);
      });
    }
  }
};
</script>

<style>
</style>
