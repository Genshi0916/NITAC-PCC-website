<template>
  <v-card
    max-width="540"
    class="mx-auto"
  >
    <v-container>
      <v-row dense>
        <v-col v-for="(item, i) in items"
          :key="i"
          cols="12">
          <a v-bind:href="item.url" target="_brank">
            <v-card
              :color="item.color"
              dark
            >
              <v-card-subtitle v-text="item.day" class="headline"></v-card-subtitle>
              <v-card-text v-text="item.text"></v-card-text>
            </v-card>
          </a>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>
<script>
export default{
  data:()=>({
    items:[
      {
        day:"2020/10/14",
        text:"第2回 SA²NCT",
        color:"#626e74",
        url:"https://sanct.connpass.com/event/188356/",
      },
      {
        day:"2019/12/16",
        text:"第1回 SA²NCT",
        color:"#385F73",
        url:"https://sanct.connpass.com/event/154446/",
      },
    ]
  })
}
</script>
<style>
  a{
    text-decoration: none;
  }
</style>
