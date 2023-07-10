<template>
 <b-container>
  <title>{{ page.title }}</title>
  <article>
   <h1>{{ page.title }}</h1>
 <nuxt-content :document="page" />
 </article>
 </b-container>
</template>
 
<script>
export default {
 async asyncData ({ $content , params }) {
  const slug = params.slug;
  const page = await $content('post/'+slug).fetch()
 
  return {
   page
  }
 }
}
</script>