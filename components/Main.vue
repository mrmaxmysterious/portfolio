<template>
  <div class="container mx-auto my-auto place-content-center font-semibold p-10 rounded-md">
    <Welcome />
    <br />
    <div class="grid gap-4 md:grid-cols-2 md:grid-rows-3 grid-cols-1 grid-rows-2" >
      <AboutMe />
      <Discord :lanyard="lanyard" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lanyard: null,
    };
  },
  async mounted() {
    const response = await this.$lanyard({
      userId: "728318691716104222",
    });
    this.lanyard = response.data;
  },
};
</script>