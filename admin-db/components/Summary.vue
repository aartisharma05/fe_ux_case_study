<!-- Summary.vue -->
<template>
  <div class="col-md-12 col-xl-4">
    <div v-for="(item, index) in summary" :key="index" class="card comp-card">
      <div class="card-body">
        <div class="row align-items-center">
          <div class="col">
            <h6 class="m-b-25">{{ item.title }}</h6>
            <h3 class="f-w-700">{{ item.value }}</h3>
            <p class="m-b-0">{{ item.duration }} ({{ item.year }})</p>
          </div>
          <div class="col-auto">
            <i :class="iconClass(item.title)"></i>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    summary: {
      type: Array,
      required: true,
    },
  },
  methods: {
    iconClass(title) {
      switch (title.toLowerCase()) {
        case "impressions":
          return "fas fa-eye";
        case "goal":
          return "fas fa-bullseye";
        case "impact":
          return "fas fa-hand-paper";
        default:
          return "";
      }
    },
    itemIconBg(title) {
      switch (title.toLowerCase()) {
        case "impressions":
          return "bg-c-blue";
        case "goal":
          return "bg-c-green";
        case "impact":
          return "bg-c-yellow";
        default:
          return "";
      }
    },
  },
};
</script>

<style scoped>
/* Add your component-specific styles here */
</style>
