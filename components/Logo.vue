<template>
  <v-layout>
    <v-flex class="text-center">
      <img
        src="logo.png"
        alt="logo"
        id="logo"
      >
      <blockquote class="blockquote" id="center">
        <p>National Institute of Technology Asahikawa College,<br>Personal Computer Club</p>
      </blockquote>
    </v-flex>
  </v-layout>
</template>

<style scoped>

  #logo{
    width: 300px;
  }

  #center{
    display: flex;
    justify-content: center;
    align-items: center;
    padding-right: 24px;
  }

  @media screen and (min-width:0px) and ( max-width:480px){
    #logo{
      padding-top: 60px;
      width: 200px;
    }
  }

  @media screen and (min-width:480px) and (max-width:768px){
    #logo{
      padding-top: 70px;
      width: 225px;
    }
  }

  @media screen and (min-width:768px) and ( max-width:1024px){
    #logo{
      padding-top: 80px;
      width: 250px;
    }
  }

  @media screen and (min-width:1024px) and ( max-width:1400px){
    #logo{
      padding-top: 90px;
      width: 275px;
    }
  }

  @media screen and (min-width:1400px){
    #logo{
      padding-top: 120px;
      width: 300px;
    }
  }
</style>
