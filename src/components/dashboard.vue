<template>
  <div class="dashboard">
    <div class="card profile">
      <div class="intro">
        <div class="image_wrapper">
          <img src="../assets/images/image-jeremy.png" />
        </div>
      </div>
      <div class="filter">
        <ul>
          <li v-for="(filter, index) in filters" :key="index">
            {{ filter.name }}
          </li>
        </ul>
      </div>
    </div>
    <div
      v-for="(item, index) in data"
      :key="index"
      :class="item.title.toLowerCase().replace(/\s/g, '')"
      class="card"
    >
      <div v-if="item.title == 'Work'" class="content">
        {{ item.title }}
      </div>
      <div v-if="item.title == 'Play'" class="content">
        {{ item.title }}
      </div>
      <div v-if="item.title == 'Study'" class="content">
        {{ item.title }}
      </div>
      <div v-if="item.title == 'Exercise'" class="content">
        {{ item.title }}
      </div>
      <div v-if="item.title == 'Social'" class="content">
        {{ item.title }}
      </div>
      <div v-if="item.title == 'Self Care'" class="content">
        {{ item.title }}
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";
import userjson from "@/assets/data.json";

export default defineComponent({
  setup() {
    let data = ref<any>(userjson);
    const filters = ref([
      { name: "Daily", value: "daily" },
      { name: "Month", value: "month" },
      { name: "Weekly", value: "weekly" },
    ]);

    return {
      data,
      filters,
    };
  },
});
</script>
