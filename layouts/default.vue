<template>
  <div class="md:container md:mx-auto">

    <div class="flex">
      <div class="flex-1">
        <img class="w-32 md:w-48 ml-4 mt-4 md:m-5" src="bartdesign.cz-logo.png" />
      </div>
      <div class="mt-auto md:mb-8 mr-8">
        <img class="w-16" src="tmp-social-icons.png" />
      </div>
    </div>

    <Nuxt />

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
