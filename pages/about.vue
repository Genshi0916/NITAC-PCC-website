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
        <v-col
          v-for="(item, i) in items"
          :key="i"
          cols="12"
        >
          <v-card dark>
            <div class="justify-space-between" v-if="$vuetify.breakpoint.mobile">
              <div>
                <v-card-title
                  class="headline"
                  v-text="item.title"
                ></v-card-title>
              </div>
              <a v-bind:href="item.url" target="_blank">
                <v-avatar
                  class="ma-3"
                  size="230"
                  tile
                >
                  <v-img :src="item.icon" id="size"></v-img>
                </v-avatar>
              </a>
            </div>
            <div class="d-flex justify-space-between" v-if="!$vuetify.breakpoint.mobile">
              <div>
                <v-card-title
                  class="headline"
                  v-text="item.title"
                ></v-card-title>
              </div>
              <a v-bind:href="item.url" target="_blank">
                <v-avatar
                  class="ma-3"
                  size="260"
                  tile
                >
                  <v-img :src="item.icon" id="size"></v-img>
                </v-avatar>
              </a>
            </div>
          </v-card>
        </v-col>
    </v-flex>
  </v-layout>
</template>
<script>
  export default
  {
    name:'about',
    components:
    {

    },
    data:()=>
    ({
      items:
      [
        {
          title:"ANCT-PCC",
          url:"https://twitter.com/ANCT_PCC",
          icon:require("../static/logo1.jpg")
        },
        {
          title:"sanct",
          url:"https://sanct.connpass.com/",
          icon:require("../static/sanct.jpeg")
        },
        {
          title:"サイト制作者",
          url:"http://genshi0916.github.io/",
          icon:require("../static/genshi.jpg")
        }
      ]
    })
  }
</script>
<style>
  #size
  {
    height:250px;
  }
</style>
