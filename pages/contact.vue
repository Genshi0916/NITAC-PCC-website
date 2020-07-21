<template>
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
          <v-btn color="blue darken-1" text to='/'>Close</v-btn>
          <v-btn color="blue darken-1" text to='/' @click="submit">Send</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
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
      const name = this.name
      const email = this.email
      const description = this.description

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
        alert('送信完了')
      })
    }
  }
}
</script>
