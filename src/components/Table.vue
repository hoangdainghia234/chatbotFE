<template>
    <div>
        <Button style="margin: 23px" />
        <Setting style="float: right; margin-top: -59px; margin-right: 52px;" />
        <v-container style="border: 1px solid; margin-top: 45px;">
            <v-simple-table style="border: 1px solid; text-align: center">
                <template v-slot:default>
                <thead>
                    <tr>
                        <th class="text-left">STT</th>
                        <th class="text-left">Project name</th>
                        <th class="text-left">Join Date</th>
                        <th class="text-left">Action</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in desserts" :key="item.name">
                    <td>{{ item.id }}</td>
                    <td>{{ item.projectName }}</td>
                    <td>{{ item.JoinDate }}</td>
                    <td>{{ item.action }}</td>
                    </tr>
                </tbody>
                </template>
            </v-simple-table>
        </v-container>
        <List />
    </div>
</template>
<script>
import Button from '../components/Button'
import Setting from '../components/Setting'
import List from '../components/list'
  export default {
    data () {
      return {
        desserts: [
          {
            id: 1,
            projectName: 'Daily meeting',
            JoinDate: '26-01-2020',
            action: 'Edit | Delete'
          },
          {
            id: 2,
            projectName: 'Weekly meeting',
            JoinDate: '15-05-2020',
            action: 'Edit | Delete'
          },
          {
            id: 3,
            projectName: 'Monthly meeting',
            JoinDate: '26-01-2020',
            action: 'Edit | Delete'
          },
        ],
      }
    },
    components: {
      Button,
      Setting,
      List
    }
  }
</script>
<style scoped>
  tr td {
      border: 1px solid;
  }
  tr th {
      border: 1px solid;
      background: rgb(56, 218, 42);
  }
  .wrapper {
    border: 1px solid;
    position: absolute;
  }
</style>>
