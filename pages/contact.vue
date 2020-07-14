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
                <v-text-field label="お名前" required></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="メールアドレス" required></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-textarea label="問い合わせ内容" outlined required ></v-textarea>
              </v-col>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text to='/'>Close</v-btn>
          <v-btn color="blue darken-1" text @click="dialog = false">Send</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  data:()=>({
    dialog:true
  })
}
</script>