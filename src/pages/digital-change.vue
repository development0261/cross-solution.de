<template>
  <q-page padding>
    <h1>Digitaler Wandel</h1>
    <p>
      Die Welt verändert sich. Das ist nichts Neues. Sie hat sich schon immer verändert.
      Sie verändert sich nur schneller.
    </p>
    <p>
      Wir sehen einen Zusammenhang zwischen Open Source und Arbeit. Und wir
      glauben, dass man einen Vorteil hat, wenn man dies erkennt.
    </p>
    <div class="q-pa-md q-gutter-sm">
      <q-btn
        label="YAWIK Demo"
        color="primary"
        @click="layout = true"
      />

      <q-dialog v-model="layout">
        <q-layout
          view="Lhh lpR fff"
          container
          class="bg-white"
        >
          <q-header class="bg-primary">
            <q-toolbar>
              <q-btn
                flat
                @click="drawer = !drawer"
                round
                dense
                icon="menu"
              />
              <q-toolbar-title>YAWIK Demo</q-toolbar-title>
              <q-btn
                flat
                @click="drawerR = !drawerR"
                round
                dense
                icon="menu"
              />
              <q-btn
                flat
                v-close-popup
                round
                dense
                icon="close"
              />
            </q-toolbar>
          </q-header>

          <q-footer class="bg-black text-white">
            <q-toolbar inset>
              <q-toolbar-title>Footer</q-toolbar-title>
            </q-toolbar>
          </q-footer>

          <q-drawer
            bordered
            v-model="drawer"
            :width="200"
            :breakpoint="600"
            content-class="bg-grey-3 q-pa-sm"
          >
            <div
              v-for="n in 50"
              :key="n"
            >Drawer {{ n }} / 50</div>
          </q-drawer>

          <q-drawer
            side="right"
            bordered
            v-model="drawerR"
            :width="200"
            :breakpoint="300"
            content-class="bg-grey-3 q-pa-sm"
          >
            <div
              v-for="n in 50"
              :key="n"
            >Drawer {{ n }} / 50</div>
          </q-drawer>

          <q-page-container>
            <q-page padding>
              <jobsearch />
            </q-page>
          </q-page-container>
        </q-layout>
      </q-dialog>
    </div>
  </q-page>
</template>

<script>

import Jobsearch from '../components/Jobsearch.vue'

export default {
  meta: {
    'title': 'Der digitale Wandel'
  },
  name: 'DigitalChange',
  data () {
    return {
      layout: false,

      moreContent: true,
      drawer: false,
      drawerR: false,

      lorem: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Natus, ratione eum minus fuga, quasi dicta facilis corporis magnam, suscipit at quo nostrum!'
    }
  },
  computed: {
    contentSize () {
      return this.moreContent ? 150 : 5
    }
  },
  components: {
    Jobsearch
  }
}
</script>
