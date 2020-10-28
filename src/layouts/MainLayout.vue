<template>
  <q-layout view="hHh Lpr lFf">
    <q-header elevated class="bg-secondary text-white">
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
          Order Management
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
<!-- Dashboard -->

     <q-item
          clickable
          tag="a"
          to="/dashboard"
        >
          <q-item-section
          avatar     
          >
            <q-icon name="dashboard" class="text-secondary"/>
          </q-item-section>

          <q-item-section>
            <q-item-label>Dashboard</q-item-label>
          </q-item-section>
        </q-item>

        <q-separator />

<!-- Orders -->
      <q-item-label header>Orders</q-item-label>

        <q-item
          clickable
          tag="a"
          to="/order-create"
        >
          <q-item-section
          avatar     
          >
            <q-icon name="assignment" class="text-secondary"/>
          </q-item-section>

          <q-item-section>
            <q-item-label>Create Order</q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable
          tag="a"
          to="/orders-list"
        >
          <q-item-section
          avatar     
          >
            <q-icon name="view_list" class="text-secondary"/>
          </q-item-section>

          <q-item-section>
            <q-item-label>Orders List</q-item-label>
          </q-item-section>
        </q-item>        
 
       <q-separator />
<!-- Invoices-->
      <q-item-label header>Invoices</q-item-label>

        <q-item
          clickable
          tag="a"
          to="/invoice-create"
        >
          <q-item-section
          avatar     
          >
            <q-icon name="assignment" class="text-secondary"/>
          </q-item-section>

          <q-item-section>
            <q-item-label>Invoice Create</q-item-label>
          </q-item-section>
        </q-item>   

        <q-item
          clickable
          tag="a"
          to="/invoice-list"
        >
          <q-item-section
          avatar     
          >
            <q-icon name="view_list" class="text-secondary"/>
          </q-item-section>

          <q-item-section>
            <q-item-label>Invoice List</q-item-label>
          </q-item-section>
        </q-item>                   

       <q-separator />

      </q-list>
    </q-drawer>

    <q-page-container class="q-ma-md">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Order Create',
    //caption: 'quasar.dev',
    icon: 'assignment',
    link: '/order-create'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>
