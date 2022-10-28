<template>
  <div class="dashboard">
    <div class="card profile">
      <div class="intro">
        <div class="image_wrapper">
          <img src="../assets/images/image-jeremy.png" />
        </div>
        <div class="intro--content">
          <p>Report for</p>
          <h1>Jermey Robson</h1>
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
        <div class="content--header">
          {{ item.title }}
          <div>
            <img src="../assets/images/icon-ellipsis.svg" alt="icon" />
          </div>
        </div>
        <div class="content--body">
          <h1>{{ item.timeframes.weekly.current }}hrs</h1>
          <p>Last-Week - {{ item.timeframes.weekly.previous }}hrs</p>
        </div>
      </div>
      <div v-if="item.title == 'Play'" class="content">
        <div class="content--header">
          {{ item.title }}
          <div>
            <img src="../assets/images/icon-ellipsis.svg" alt="icon" />
          </div>
        </div>
        <div class="content--body">
          <h1>{{ item.timeframes.weekly.current }}hrs</h1>
          <p>Last-Week - {{ item.timeframes.weekly.previous }}hrs</p>
        </div>
      </div>
      <div v-if="item.title == 'Study'" class="content">
        <div class="content--header">
          {{ item.title }}
          <div>
            <img src="../assets/images/icon-ellipsis.svg" alt="icon" />
          </div>
        </div>
        <div class="content--body">
          <h1>{{ item.timeframes.weekly.current }}hrs</h1>
          <p>Last-Week - {{ item.timeframes.weekly.previous }}hrs</p>
        </div>
      </div>
      <div v-if="item.title == 'Exercise'" class="content">
        <div class="content--header">
          {{ item.title }}
          <div>
            <img src="../assets/images/icon-ellipsis.svg" alt="icon" />
          </div>
        </div>
        <div class="content--body">
          <h1>{{ item.timeframes.weekly.current }}hrs</h1>
          <p>Last-Week - {{ item.timeframes.weekly.previous }}hrs</p>
        </div>
      </div>
      <div v-if="item.title == 'Social'" class="content">
        <div class="content--header">
          {{ item.title }}
          <div>
            <img src="../assets/images/icon-ellipsis.svg" alt="icon" />
          </div>
        </div>
        <div class="content--body">
          <h1>{{ item.timeframes.weekly.current }}hrs</h1>
          <p>Last-Week - {{ item.timeframes.weekly.previous }}hrs</p>
        </div>
      </div>
      <div v-if="item.title == 'Self Care'" class="content">
        <div class="content--header">
          {{ item.title }}
          <div>
            <img src="../assets/images/icon-ellipsis.svg" alt="icon" />
          </div>
        </div>
        <div class="content--body">
          <h1>{{ item.timeframes.weekly.current }}hrs</h1>
          <p>Last-Week - {{ item.timeframes.weekly.previous }}hrs</p>
        </div>
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
