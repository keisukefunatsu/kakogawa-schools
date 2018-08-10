<template>
  <div class="container">
    <nav class="panel">
      <p class="panel-heading">
        {{school.学校名}}
      </p>
      <div class="panel-block" v-for="(v, k) in school" :key="k">
        <span class="panel-icon">
          <i class="fas fa-book" aria-hidden="true"></i>          
        </span>
        {{k}} : {{v}}
      </div>
    </nav>
  </div>
</template>

<script>
import schools from "~/stu_29_latlng.json";
export default {
  head() {
    return {
      title: this.school.学校名 + "の情報"
    };
  },
  asyncData({ params }, callback) {
    let school = schools.find(school => school.学校名 == params.name);
    if (school) {
      callback(null, { school });
    } else {
      callback({ statusCode: 404, message: "school not found" });
    }
  }
};
</script>