<template>
  <div class="row justify-center">
    <div class="col-xs-12 col-sm-12 col-md-10 col-lg-10">
      <q-layout view="hhh lpr lfr">
        <q-header elevated>
          <q-toolbar>
            <q-btn
              flat
              dense
              round
              @click="leftDrawerOpen = !leftDrawerOpen"
              icon="menu"
              aria-label="Menu"
            />

            <q-toolbar-title>
              투두이스트 클론
            </q-toolbar-title>

            <div>Quasar v{{ $q.version }}</div>
          </q-toolbar>
        </q-header>

        <q-drawer
          side="left"
          v-model="leftDrawerOpen"
          show-if-above
          :breakpoint="750"
          bordered
          content-class="bg-grey-2"
        >
          <q-list>
            <q-item-label header>Essential Links</q-item-label>
            <q-item clickable tag="a" target="_blank" href="https://quasar.dev">
              <q-item-section avatar>
                <q-icon name="school"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Docs</q-item-label>
                <q-item-label caption>quasar.dev</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable tag="a" target="_blank" href="https://github.quasar.dev">
              <q-item-section avatar>
                <q-icon name="code"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Github</q-item-label>
                <q-item-label caption>github.com/quasarframework</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable tag="a" target="_blank" href="https://chat.quasar.dev">
              <q-item-section avatar>
                <q-icon name="chat"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Discord Chat Channel</q-item-label>
                <q-item-label caption>chat.quasar.dev</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable tag="a" target="_blank" href="https://forum.quasar.dev">
              <q-item-section avatar>
                <q-icon name="record_voice_over"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Forum</q-item-label>
                <q-item-label caption>forum.quasar.dev</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable tag="a" target="_blank" href="https://twitter.quasar.dev">
              <q-item-section avatar>
                <q-icon name="rss_feed"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Twitter</q-item-label>
                <q-item-label caption>@quasarframework</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable tag="a" target="_blank" href="https://facebook.quasar.dev">
              <q-item-section avatar>
                <q-icon name="public"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Facebook</q-item-label>
                <q-item-label caption>@QuasarFramework</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-drawer>

        <q-page-container>
          <router-view/>
        </q-page-container>
      </q-layout>
    </div>
  </div>
</template>

<script>
    export default {
        name: 'MyLayout',

        data() {
            return {
                leftDrawerOpen: false
            }
        }
    }
</script>
