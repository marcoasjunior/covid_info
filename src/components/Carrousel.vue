<template>
    <div class="row justify-center">
    <q-card class="my-card">
        <q-carousel
        animated
        v-model="slide"
        swipeable
        infinite
        autoplay
        arrows
        transition-prev="slide-right"
        transition-next="slide-left"
        height="400px"
        >
        <q-carousel-slide name="soft-jazz">
            <iframe width="560" height="350" src="https://www.youtube.com/embed/bPITHEiFWLc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </q-carousel-slide>

        <q-carousel-slide name="Rihanna">
            <iframe width="560" height="350" src="https://www.youtube.com/embed/M4olt47pr_o" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </q-carousel-slide>

        <q-carousel-slide name="chill-mix">
            <iframe width="560" height="350" src="https://www.youtube.com/embed/Ded_AxFfJoQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </q-carousel-slide>
        </q-carousel>
    </q-card>
    </div>
</template>

<script>
export default {
  data () {
    return {
      slide: 'Rihanna'
    }
  }
}
</script>

<style scoped>
    .my-card {
        width: 100%;
        max-width: 580px;
        height: 400px;
        max-height: 600px;
    }
</style>
