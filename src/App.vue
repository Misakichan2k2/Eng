<script setup>
import topbar from "./topbar.vue";
import left from "./left.vue";
import myClassroom from "./myClassroom.vue";
import joinedClassroom from "./joinedClassroom.vue";
import profile from "./profile.vue";
</script>

<template>
  <div class="flex flex-column relative">
    <!-- Top bar -->
    <topbar />

    <!-- Content -->
    <div class="flex">
      <!-- Left -->
      <left />
      <!-- Right -->
      <div>
        <myClassroom />
        <!-- <joinedClassroom /> -->
        <!-- <profile /> -->
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
