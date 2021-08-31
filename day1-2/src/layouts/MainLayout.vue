<template>
  <q-layout view="lHr lpR fFf">

    <q-header bordered class="bg-white text-black">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title class="text-weight-bold">
          {{ $route.name }}
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" 
    side="left" bordered>
      <!-- drawer content -->
      <q-icon 
      class='q-pa-md'
      name="fas fa-dove"
      size='lg'
      color='primary'
      />

      <q-list>
      <q-item 
        to="/"
        clickable 
        v-ripple
        exact
        >
        <q-item-section avatar>
          <q-icon name="home" size='md'/>
        </q-item-section>

        <q-item-section class='text-h6'>Home</q-item-section>
      </q-item>

      <q-item 
        to="/about"
        clickable 
        v-ripple
        exact
        >
        <q-item-section avatar>
          <q-icon name="help" size='md'/>
        </q-item-section>

        <q-item-section class='text-h6'>About</q-item-section>
      </q-item>
      

      
    </q-list>
    </q-drawer>

    <q-drawer 
    show-if-above 
    side="right" 
    bordered
    >
    <q-input
    placeholder="Search Twitter"
    class="q-ma-md"
    outlined
    rounded
    dense
    >
        <template v-slot:prepend>
          <q-icon name="search" />
        </template>
      </q-input>

    <q-list 
    padding
    separator
    >
      <q-item class="q-pa-md">
        <q-item-section>
          <q-item-label overline 
          class="text-grey">Entertainment Trending</q-item-label>
          <q-item-label
          class="text-weight-bold">無料10連</q-item-label>
          <q-item-label caption>7,222 Tweet</q-item-label>
        </q-item-section>

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
        </q-item-section>
      </q-item>
      <q-item class="q-pa-md">
        <q-item-section>
          <q-item-label overline 
          class="text-grey">Entertainment Trending</q-item-label>
          <q-item-label
          class="text-weight-bold">無料10連</q-item-label>
          <q-item-label caption>7,222 Tweet</q-item-label>
        </q-item-section>

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
        </q-item-section>
      </q-item>
      <q-item class="q-pa-md">
        <q-item-section>
          <q-item-label overline 
          class="text-grey">Entertainment Trending</q-item-label>
          <q-item-label
          class="text-weight-bold">無料10連</q-item-label>
          <q-item-label caption>7,222 Tweet</q-item-label>
        </q-item-section>

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },

      rightDrawerOpen,
      toggleRightDrawer () {
        rightDrawerOpen.value = !rightDrawerOpen.value
      }
    }
  }
}
</script>