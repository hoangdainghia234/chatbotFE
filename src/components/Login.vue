<template>
    <v-app>
        <v-container>
            <v-row align="center" justify="center">
                <v-col cols="12" sm="8" md="4">
                    <v-card class="elevation-12">
                        <v-card-text>
                            <v-form>
                                <v-text-field outlined label="Name" required></v-text-field>
                                <v-text-field outlined label="Your Slack id" required></v-text-field>
                                <v-dialog ref="dialog" v-model="modal2" :return-value.sync="time" persistent width="290px">
                                    <template v-slot:activator="{ on }">
                                        <v-text-field outlined v-model="time" label="Your meeting time" readonly v-on="on"></v-text-field>
                                    </template>
                                    <v-time-picker v-if="modal2" v-model="time" full-width>
                                        <v-spacer></v-spacer>
                                        <v-btn text color="primary" @click="modal2 = false">Cancel</v-btn>
                                        <v-btn text color="primary" @click="$refs.dialog.save(time)">OK</v-btn>
                                    </v-time-picker>
                                </v-dialog>
                                <v-card-actions style="margin-right: 15px">
                                    <v-btn x-large color="success" dark>Add your account</v-btn>
                                </v-card-actions>
                            </v-form>
                        </v-card-text>
                    </v-card>
                </v-col>
          </v-row>
        </v-container>
    </v-app>
</template>
<script>
export default {
  data () {
    return {
      time: null,
      menu2: false,
      modal2: false,
    }
  }
}
</script>
