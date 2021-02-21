<template>
  <v-layout wrap>
    <v-spacer></v-spacer>
    <v-btn to='/' text>Home</v-btn>
    <v-btn
      v-for="item in items"
      :key="item.to"
      :to="item.to" text>{{item.text}}
    </v-btn>
  </v-layout>
</template>

<script>
export default{
  name:'header',
  data:()=>({
    items:[
      {
        to:'/activities',
        text:'activities'
      },
      {
        to:'/contact',
        text:'contact'
      },
      {
        to:'/about',
        text:'about'
      },
    ]
  })
}
</script>

<style>
.link{
  text-decoration:none;
}
</style>
