<template>
 <div id="app">
    <v-row justify="right">
      <v-dialog v-model="dialog" persistent max-width="600px">
        <template v-slot:activator="{ on }">
          <v-btn color="success" dark v-on="on">Setting</v-btn>
        </template>
        <v-card>
          <v-card-title>
            <span class="headline">Setting</span>
          </v-card-title>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col cols="12">
                  <v-text-field outlined label="Name" required></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-select outlined
                    :items="['asd#4123#asd', 'dsd#523#fsd', 'rsvd#4123#asd', 'advvd#4123#asd']"
                    label="Your slack id"
                    required
                  ></v-select>
                </v-col>

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
              </v-row>
            </v-container>
          </v-card-text>
          <v-card-actions justify="center">
            <v-spacer></v-spacer>
            <v-btn color="blue darken-1" text @click="dialog = false">Close</v-btn>
            <v-btn color="blue darken-1" text @click="dialog = false">Save</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
 </div>
</template>
<script>
export default {
    data () {
        return {
            dialog: false,
            items: ['user1', 'user2', 'user3', 'user4'],
            value: ['user1', 'user2', 'user3', 'user4'],
            time: null,
            menu2: false,
            modal2: false,
        }
    }
}
</script>
