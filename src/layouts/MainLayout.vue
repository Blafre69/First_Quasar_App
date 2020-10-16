<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          Shopping List
        </q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-list bordered padding>
        <q-item clickable v-ripple to="/shoppinglist">
        <q-item-section avatar>
          <q-icon color="primary" name="list" />
        </q-item-section>

        <q-item-section>Shopping List</q-item-section>
      </q-item>
      <q-separator/>
      <q-item clickable v-ripple to="/">
        <q-item-section avatar>
          <q-icon color="primary" name="lock" />
        </q-item-section>

        <q-item-section>Sign Out</q-item-section>
      </q-item>
      </q-list>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',
  data () {
    return {
      leftDrawerOpen: false
    }
  }
}
</script>
