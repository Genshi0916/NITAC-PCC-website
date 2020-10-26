<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="text-center">
        <Logo/>
      </div>
      <v-card>
        <v-card-title class="headline">
          旭川高専パソコン部へようこそ！！！！
        </v-card-title>
        <v-card-text>
          <p>
            旭川高専パソコン部ではプログラミング、イラスト制作、動画制作など様々な分野での活動を行っています！
          </p>
          <p>秀峰会館2階で平日放課後に気ままに活動！パソコン部で待ってます！</p>
        </v-card-text>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  import Logo from '~/components/Logo.vue'
  export default {
    components: {
      Logo,
    }
  }
</script>
