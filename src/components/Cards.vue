<template>
  <div class="q-pa-md">
      <div class="row q-gutter-md items-center justify-around" >
    <q-card class="my-card">
      <img src="..\statics\img1-maos.png">

      <q-card-section>
        <div class="text-h6">Lave as mãos com água e sabão ou use álcool em gel.</div>
      </q-card-section>

    </q-card>
    <q-card class="my-card">
      <img src="..\statics\img2-tosse.png">

      <q-card-section>
        <div class="text-h6">Cubra o nariz e boca ao espirrar ou tossir.</div>
      </q-card-section>

    </q-card>
    <q-card class="my-card">
      <img src="..\statics\img3-pessoas.png">

      <q-card-section>
        <div class="text-h6">Evite aglomerações se estiver doente.</div>
      </q-card-section>

    </q-card>
    <q-card class="my-card">
      <img src="..\statics\img4-janela.png">

      <q-card-section>
        <div class="text-h6">Mantenha os ambientes bem ventilados.</div>
      </q-card-section>

    </q-card>
    <q-card class="my-card">
      <img src="..\statics\img5-objetos.png">

      <q-card-section>
        <div class="text-h6">Não compartilhe objetos pessoais.</div>
      </q-card-section>

    </q-card>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cards',
  data () {
    return {
      lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
    }
  }
}
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 250px
  height: 400px

img
    margin-top: 10px
</style>
