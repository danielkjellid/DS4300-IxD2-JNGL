<template>
  <!-- components to show review stars accross app -->
  <div class="flex items-center mt-1">
     <!-- review stars, dynamically 'coloring' based on the place's assesment -->
    <svg v-for="(star, index) in 5" :key="index" class="w-4 h-4" fill="currentColor" :class="index >= conditional ? 'text-gray-400' : 'text-gray-800'">
      <path d="M5.256 1.006c.295-.93 1.611-.93 1.906 0l.764 2.408a1 1 0 00.953.697H11.4c.963 0 1.37 1.228.597 1.803l-2.081 1.55a1 1 0 00-.356 1.104l.785 2.475c.293.926-.772 1.685-1.55 1.105l-1.989-1.48a1 1 0 00-1.194 0l-1.989 1.48c-.778.58-1.843-.179-1.55-1.105l.785-2.475a1 1 0 00-.356-1.105L.421 5.913c-.773-.574-.366-1.802.597-1.802h2.521a1 1 0 00.953-.697l.764-2.408z" />
    </svg>
  </div>
</template>

<script>
export default {
  name: 'CoreStars',
  props: {
    conditional: {
      type: Number,
      required: true,
      default: 0,
    }
  }
}
</script>

<style>

</style>