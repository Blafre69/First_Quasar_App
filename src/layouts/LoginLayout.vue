<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-light-blue-7">
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

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-3"
      :breakpoint="500"
    >
    <q-scroll-area style="heigh: calc(100% - 15Opx); margin-top: 150px; border-right: 1px solid #ddd"/>
      <q-list border padding>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon color="primary" name="list"/>
          </q-item-section>
          <q-item-section>Shopping List</q-item-section>
        </q-item>
      <q-separator/>
      <q-item clickable v-ripple>
        <q-item-section avatar>
          <q-icon color="primary" name="lock"/>
        </q-item-section>
        <q-item-section>Sign out </q-item-section>
      </q-item>
      </q-list>
      <q-img class="absolute-top" src ="../assets/food.jpg" style ="height: 150px">
        <div class="absolute-bottom bg-transparent">
          <q-avatar size="56px" class="q-mb-sm">
            <img src="../assets/avatar.png">
          </q-avatar>
        </div>
      </q-img>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'LoginLayout',
  data () {
    return {
      leftDrawerOpen: true
    }
  }
}
</script>
