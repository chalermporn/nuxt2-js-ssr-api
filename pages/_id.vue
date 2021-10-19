<template>
  <div class="w-screen flex items-center justify-center text-red-500">
    <div class="container pt-10 px-10">
      <figure class="md:flex bg-gray-100 rounded-xl p-8 md:p-0">
        <img
          class="w-32 h-32 md:w-48 md:h-auto md:rounded-none rounded-full mx-auto"
          :src="data.image"
          alt
          width="384"
          height="512"
        />
        <div class="pt-6 md:p-8 text-center md:text-left space-y-4">
          <blockquote>
            <p class="text-lg font-semibold">{{ data.description }}</p>
          </blockquote>
          <figcaption class="font-medium">
            <div class="text-cyan-600">{{ data.title }}</div>
            <div class="text-gray-500">
              <span v-for="(c, i) in data.countries" :key="i">{{ c }},</span>
            </div>
          </figcaption>
        </div>
      </figure>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, params }) {
    const data = await $axios.$get(`https://api.nuxtjs.dev/posts/${params.id}`)
    // eslint-disable-next-line no-console
    // console.log(data);
    return { data }
  }
}
</script>