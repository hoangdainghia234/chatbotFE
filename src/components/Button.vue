<template>
 <div id="app">
    <v-row justify="left">
      <v-dialog v-model="dialog" persistent max-width="600px">
        <template v-slot:activator="{ on }">
          <v-btn color="primary" dark v-on="on">Create new project</v-btn>
        </template>
        <v-card>
          <v-card-title>
            <span class="headline">User Profile</span>
          </v-card-title>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col cols="12">
                  <v-text-field outlined label="project name" required></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-select outlined
                    :items="['0-17', '18-29', '30-54', '54+']"
                    label="slack id"
                    required
                  ></v-select>
                </v-col>
                <v-col cols="12">
                  <v-text-field outlined label="Bot-key" required></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-text-field outlined label="Bot avatar link" type="text" required></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-text-field outlined label="Bot name" type="text" required></v-text-field>
                </v-col>

                <v-col cols="12" sm="6">
                  <v-select
                    v-model="value"
                    :items="items"
                    chips
                    label="Chips"
                    multiple
                    solo
                  ></v-select>
                </v-col>
              <v-col cols="12" sm="6">
                <v-text-field
                  label="Tyle name"
                  outlined
                  rounded
                  dense
                ></v-text-field>
              </v-col>
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
        }
    }
}
</script>>