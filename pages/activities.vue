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
          <v-card
            :color="item.color"
            dark
          >
            <v-card-subtitle v-text="item.year" class="headline"></v-card-subtitle>
            <v-card-subtitle v-text="item.text"></v-card-subtitle>
          </v-card>
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
        year:"2012年",
        text:"全国高等専門学校第23回プログラミングコンテスト課題部門 佳作",
        color:"#626e74"
      },
      {
        year:"2013年",
        text:"全国高等専門学校第24回プログラミングコンテスト課題部門 敢闘賞",
        color:"#385F73"
      },
      {
        year:"2014年",
        text:"全国高等専門学校第25回プログラミングコンテスト課題部門 敢闘賞",
        color:"#626e74"
      },
      {
        year:"2015年",
        text:"全国高等専門学校第26回プログラミングコンテスト競技部門 特別賞",
        color:"#385F73"
      },
      {
        year:"2016年",
        text:"全国高等専門学校第23回プログラミングコンテスト 競技部門",
        color:"#626e74"
      },
      {
        year:"2017年",
        text:"全国高等専門学校第23回プログラミングコンテスト 競技部門",
        color:"#385F73"
      },
      {
        year:"2018年",
        text:"全国高等専門学校第23回プログラミングコンテスト競技部門",
        color:"#626e74"
      },
      {
        year:"2019年",
        text:"全国高等専門学校第23回プログラミングコンテスト競技部門 台風により参加ならず",
        color:"#385F73"
      },
      {
        year:"2020年",
        text:"全国高等専門学校第23回プログラミングコンテスト競技部門 開催中止",
        color:"#626e74"
      },
    ]
  })
}
</script>
