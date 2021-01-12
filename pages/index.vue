<template>
  <div>
    <div class="flex flex-wrap font-mono">
      <div
        class="relative w-full md:w-1/2 p-4"
        v-for="(item, index) in projects"
        :key="index"
        @click="selectProject(index)"
      >
        <div class="absolute mojetransition inset-0 rounded-xl bg-gray-700 bg-opacity-50 py-8 text-white m-4">
          <div class="absolute bottom-0 mb-4 ml-4">
            <div class="mb-2"><h1 class="text-white bg-black text-xs p-2 py-1 inline">. {{ item.slug }} .</h1></div>
            <div v-if="item.title" class=""><p class="text-black bg-white text-xs p-2 py-1 inline">{{ item.title }}</p></div>
            <div v-if="item.website"><p class="text-black bg-white text-xs p-2 py-1 inline"><a :href="item.website">{{ item.website }}</a></p></div>
          </div>
        </div>
        <img class="rounded-xl" :src="item.imgs[0]" />
      </div>

    </div>

    <div
      class="fixed inset-0 overflow-scroll bg-black bg-opacity-75"
      v-if="selectedProjectIndex != null && selectedProjectIndex >= 0 && selectedProjectIndex <= projects.length"
      @click="selectedProjectIndex = null"
    >
      <div class="absolute inset-0 m-2 md:m-12 md:mb-40"> <!--@click="$event.stopPropagation()"-->
        <div class="grid grid-cols-12 md:h-full">
          <div class="col-span-12 text-center">
            <img class="rounded-xl object-contain inline md:h-full" :src="projects[selectedProjectIndex].imgs[selectedImageIndex]" />
          </div>
        </div>
        <div class="text-center h-20">
          <div class="p-2">
            <img
              class="h-16 inline m-1 border border-white opacity-75 hover:opacity-100"
              v-for="(img, index) in projects[selectedProjectIndex].imgs"
              :key="index"
              :src="img"
              @click="selectedImageIndex = index; $event.stopPropagation();"
            />
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<style>
.mojetransition {
  transition: opacity .4s ease-out;
  @apply opacity-0;
}
.mojetransition:hover {
  transition: opacity .4s ease-out;
  @apply opacity-100;
}
</style>

<script>
export default {

  async asyncData ({ $content }) {
    const projects = await $content('projects').fetch();
    return {
      projects
    }
  },

  data: () => ({
    selectedProjectIndex: null,
    selectedImageIndex: 0
  }),

  methods: {
    selectProject: function(index) {
      this.selectedProjectIndex = index;
      this.selectedImageIndex = 0;
    }
  }

}
</script>
