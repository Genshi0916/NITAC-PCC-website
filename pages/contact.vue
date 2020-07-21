<!--><template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="600px">
      <v-card>
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
          <v-btn to="/" color="blue darken-1" text @click="check">Close</v-btn>
          <v-btn  v-on:click="submit" color="blue darken-1" tex>Send</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>-->

<template>
<v-card>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="name"
      label="お名前"
      required
    ></v-text-field>

    <v-text-field
      v-model="email"
      label="メールアドレス"
      required
    ></v-text-field>

    <v-text-field
      v-model="description"
      label="問い合わせ内容"
      required
    ></v-text-field>

      <v-btn to="/" color="blue darken-1" @click="check">Close</v-btn>
      <v-btn  v-on:click="submit" color="blue darken-1">Send</v-btn>
  </v-form>
  </v-card>
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
      const url = 'https://hooks.slack.com/services/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'

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
