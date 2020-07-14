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
            旭川高専パソコン部では
          </p>

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
