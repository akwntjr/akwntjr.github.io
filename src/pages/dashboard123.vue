<script setup lang="ts">

import ChartRadar from '@/components/demo-charts/ChartRadar.vue'
import ChartLine from '../components/demo-charts/ChartLine.vue'
import ChartBar from '../components/demo-charts/ChartBar.vue'
import ChartPie from '../components/demo-charts/ChartPie.vue'
import StatsCard from '../components/StatsCard.vue'

const dialog = ref(false);

const variants = ['elevated', 'flat', 'tonal', 'outlined', 'text', 'plain']

const stats = ref([
  {
    icon: 'mdi-web',
    title: 'Bandwidth',
    value: 230,
    unit: 'GB',
    color: 'primary',
    caption: 'Up: 100, Down: 130',
  },
  {
    icon: 'mdi-rss',
    title: 'Submissions',
    value: 108,
    color: 'primary',
    caption: 'Too young, too naive',
  },
  {
    icon: 'mdi-send',
    title: 'Requests',
    value: 1238,
    color: 'warning',
    caption: 'Limit: 1320',
  },
  {
    icon: 'mdi-bell',
    title: 'Messages',
    value: 9042,
    color: 'primary',
    caption: 'Warnings: 300, erros: 47',
  },
  {
    icon: 'mdi-github',
    title: 'Github Stars',
    value: NaN,
    color: 'grey',
    caption: 'API has no response',
  },
  {
    icon: 'mdi-currency-cny',
    title: 'Total Fee',
    value: 2300,
    unit: '￥',
    color: 'error',
    caption: 'Upper Limit: 2000 ￥',
  },
])
</script>

<template>
   <v-container class="px-6 mt-n2" fluid>
    <v-row dense>
    <v-col
      v-for="(variant, i) in variants"
      :key="i"
      cols="12"
      md="4"
    >
    <v-card
    class="mx-auto"
    max-width="344"
    outlined
  >
    <v-list-item three-line>
      <v-list-item-content>
        <div class="text-overline mb-4">
          OVERLINE
        </div>
        <v-list-item-title class="text-h5 mb-1">
          Headline 5
        </v-list-item-title>
        <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
      </v-list-item-content>

      <v-list-item-avatar
        tile
        size="80"
        color="grey"
      />
    </v-list-item>

    <v-card-actions>
      <v-row justify="center">
    <v-dialog
      v-model="dialog"
      persistent
      max-width="600px"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          dark
          v-bind="attrs"
          v-on="on"
        >
          Open Dialog
        </v-btn>
      </template>
      <v-card>
        <v-card-title>
          <span class="text-h5">User Profile</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Legal first name*"
                  required
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Legal middle name"
                  hint="example of helper text only on focus"
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Legal last name*"
                  hint="example of persistent helper text"
                  persistent-hint
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  label="Email*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  label="Password*"
                  type="password"
                  required
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
              >
                <v-select
                  :items="['0-17', '18-29', '30-54', '54+']"
                  label="Age*"
                  required
                ></v-select>
              </v-col>
              <v-col
                cols="12"
                sm="6"
              >
                <v-autocomplete
                  :items="['Skiing', 'Ice hockey', 'Soccer', 'Basketball', 'Hockey', 'Reading', 'Writing', 'Coding', 'Basejump']"
                  label="Interests"
                  multiple
                ></v-autocomplete>
              </v-col>
            </v-row>
          </v-container>
          <small>*indicates required field</small>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="blue darken-1"
            text
            @click="dialog = false"
          >
            Close
          </v-btn>
          <v-btn
            color="blue darken-1"
            text
            @click="dialog = false"
          >
            Save
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
    </v-card-actions>
  </v-card>
      <div class="text-center text-caption">{{ variant }}</div>
    </v-col>
  </v-row>
      </v-container>
</template>

<style scoped lang="scss">
.v-card:not(.stats-card) {
  height: 350px;
}
</style>

<route lang="json">
{
  "meta": {
    "title": "dashboard123",
    "icon": "mdi-monitor-dashboard",
    "drawerIndex": 1
  }
}
</route>
