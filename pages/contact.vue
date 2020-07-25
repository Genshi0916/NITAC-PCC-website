<template>
  <div>
    <v-row id="center" justify="center">
      <v-card >
        <v-card-title>
          <span class="headline">Contact Form</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12">
                <v-text-field label="お名前" required v-model="name"></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="メールアドレス" required v-model="email"></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-textarea label="問い合わせ内容" outlined required v-model="description"></v-textarea>
              </v-col>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn  v-on:click="submit" color="blue darken-1" tex>Send</v-btn>
        </v-card-actions>
      </v-card>
    </v-row>
  </div>
</template>

<script>
export default {
  data:()=>({
    dialog:true,
    name:'',
    email:'',
    description:''
  }),
  methods:{
    submit:function(){
      var name = this.name
      var email = this.email
      var description = this.description

      const payload = {
        text: '問い合わせがありました\n'+
              '名前:'+name+'\n'+
              'email:'+email+'\n'+
              '内容:'+description+'\n'
      }
      const url = 'ここにはwebhookのトークンが入ります'

      fetch(url,{
        method:'POST',
        body:JSON.stringify(payload)
      }).then(()=>{
        alert('送信完了');
        this.name="";
        this.email="";
        this.description="";
      })
    }
  }
}
</script>
<style scoped>

  @media screen and (min-width:0px) and ( max-width:480px){

  }

  @media screen and (min-width:480px) and (max-width:768px){
  #center
  {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80vh;
  }
  }

  @media screen and (min-width:768px) and ( max-width:1024px){
  #center
  {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80vh;
  }
  }

  @media screen and (min-width:1024px) and ( max-width:1400px){
    #center
    {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 80vh;
    }
  }

  @media screen and (min-width:1400px){
    #center
    {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 80vh;
    }
  }
</style>
