<template>
  <div>
    <div class="flex flex-wrap font-mono">

      <div
        class="relative w-full md:w-1/2 p-4"
        v-for="item in projects"
        :key="item.name"
      >
        <div class="absolute mojetransition inset-0 rounded-xl bg-gray-700 bg-opacity-50 py-8 text-white m-4">
          <div class="absolute bottom-0 mb-4 ml-4">
            <div class="mb-2"><h1 class="text-white bg-black text-xs p-2 py-1 inline">. {{ item.name }} .</h1></div>
            <div v-if="item.title" class=""><p class="text-black bg-white text-xs p-2 py-1 inline">{{ item.title }}</p></div>
            <div v-if="item.website"><p class="text-black bg-white text-xs p-2 py-1 inline"><a :href="item.website">{{ item.website }}</a></p></div>
          </div>
        </div>
        <img class="rounded-xl" :src="item.imgs[0]" />
      </div>

    </div>

    <div class="fixed inset-0 overflow-scroll bg-black bg-opacity-50 flex">
      aaa
    </div>
  </div>
</template>

<script>
export default {

  data: () => ({
    projects: [
      {
        name: 'Ragwear T-Shirts',
        title: 'Corporate identity - logotype',
        website: 'https://www.ragwear.com/cz',
        imgs: [
          'box2.png'
        ]
      },
      {
        name: 'iyengar yoga institute',
        title: 'consectetur adipiscing elit',
        website: 'https://iy.yoga/',
        imgs: [
          'box1.png'
        ]
      },
      {
        name: 'living flowers',
        title: 'consectetur adipiscing elit',
        website: '',
        imgs: [
          'box4.png'
        ]
      },
      {
        name: 'bla bla bla',
        title: 'dolore magna aliqua. Ut enim a',
        website: '',
        imgs: [
          'box3.png'
        ]
      },
      {
        name: 'bla bla bla',
        title: 'dolore magna aliqua. Ut enim a',
        website: '',
        imgs: [
          'box3.png'
        ]
      },
      {
        name: 'bla bla bla',
        title: 'dolore magna aliqua. Ut enim a',
        website: '',
        imgs: [
          'box3.png'
        ]
      },
      {
        name: 'bla bla bla',
        title: 'dolore magna aliqua. Ut enim a',
        website: '',
        imgs: [
          'box3.png'
        ]
      },
      {
        name: 'bla bla bla',
        title: 'dolore magna aliqua. Ut enim a',
        website: '',
        imgs: [
          'box3.png'
        ]
      },
    ]
  }),

  created: function() {
    console.log(this.projects);
  }
}
</script>
