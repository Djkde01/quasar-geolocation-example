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
          Geolocation App
        </q-toolbar-title>

        <div>
          <a
            style="text-decoration: none; color: white; font-weight: bold;"
            href="https://djkde.com"
          >
            by Djkde
          </a>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink'

export default {
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: [
        {
          title: 'Built With Quasar',
          caption: 'quasar.dev',
          icon: 'school',
          link: 'https://quasar.dev'
        },
        {
          title: 'Original Repo',
          caption: 'tomers/quasar-geolocation-example',
          icon: 'code',
          link: 'https://github.com/tomers/quasar-geolocation-example'
        },
        {
          title: 'Test Repo',
          caption: 'djkde01/quasar-geolocation-example',
          icon: 'code',
          link: 'https://github.com/Djkde01/quasar-geolocation-example'
        },
        {
          title: 'Demo Site',
          caption: 'https://quasar-geolocation-example.surge.sh',
          icon: 'open_in_browser',
          link: 'https://quasar-geolocation-example.surge.sh/'
        }
      ]
    }
  }
}
</script>
