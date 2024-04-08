<script setup>
import { ref } from "vue";

const classlist = ref([
  {
    code: 1,
    image: "/public/images/natsume02.jpg",
    name: "English Vocab",
    description: "Let's learn together!",
    author: "Guava writer",
  },
  {
    code: 2,
    image: "/public/images/natsume01.jpg",
    name: "Japanese Vocab",
    description: "Let's travel in anime world!",
    author: "Carot writer",
  },
]);

const visible = ref(false);
</script>

<template>
  <div class="relative" style="height: 32rem">
    <h2 class="m-5">JOINED CLASSROOM</h2>
    <div class="flex gap-8">
      <div v-for="classdetail in classlist" :key="classdetail.code">
        <div class="flex gap-5">
          <div class="relative">
            <span
              class="absolute ml-6 mt-2 text-2xl font-semibold text-white w-6"
              >{{ classdetail.name }}</span
            >
            <div class="ml-5 w-12rem h-12rem">
              <img
                :src="classdetail.image"
                class="w-full h-full border-round"
                style="object-fit: cover"
              />
            </div>
          </div>
          <div class="flex flex-column gap-6">
            <div class="flex flex-column">
              <span class="font-semibold">{{ classdetail.name }}</span>
              <span>{{ classdetail.description }}</span>
            </div>
            <div class="flex flex-column">
              <span class="font-semibold">Author:</span>
              <span>{{ classdetail.author }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Add Dialog -->
    <div class="card flex justify-content-center bottom-right absolute">
      <Button
        icon="pi pi-plus"
        rounded
        aria-label="Filter"
        @click="visible = true"
      />
      <Dialog
        v-model:visible="visible"
        modal
        header="Join Classroom"
        :style="{ width: '22rem' }"
      >
        <span class="p-text-secondary block mb-3"
          >Enter the code to join the classroom.</span
        >
        <div class="mb-3">
          <InputText
            v-model="value1"
            placeholder="Enter code"
            class="w-19rem"
          />
        </div>
        <div class="flex justify-content-end gap-2">
          <Button
            type="button"
            label="Cancel"
            severity="secondary"
            @click="visible = false"
          ></Button>
          <Button type="button" label="Join" @click="visible = false"></Button>
        </div>
      </Dialog>
    </div>
  </div>
</template>

<style scoped lang="scss">
.bottom-right {
  position: absolute;
  bottom: 0;
  right: 0;
}
</style>
