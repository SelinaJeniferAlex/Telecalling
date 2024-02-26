<template>
  <div id="q-app" style="min-height: 100vh;">
    <div>
      <q-layout view="hHh Lpr lff" container style="height: 100vh">
        <q-drawer
          v-model="drawer"
          show-if-above

          :mini="!drawer || miniState"
          @click.capture="drawerClick"

          :width="300"
          :breakpoint="500"
          bordered
          
          :class="$q.dark.isActive ? 'bg-indigo-13' : 'bg-indigo-14'"
        >
          <q-scroll-area class="fit" :horizontal-thumb-style="{ opacity: 0 }">
            <q-list padding>
              <br>
              <q-item class="q-ma-md text-white" clickable v-ripple>
                <q-item-section avatar class="self-start text-h5 text-weight-bold" :class="{ 'iconHide': !miniState }">
                  <q-icon name="T"></q-icon>
                </q-item-section>

                <q-item-section class="text-h5 text-center text-weight-bold">
                  TELECALLING
                </q-item-section>
              </q-item>
              <br>
              <br>
              <q-item clickable v-ripple>
                <q-item-section class="text-white" avatar>
                  <q-icon name="call"></q-icon>
                </q-item-section>

                <q-item-section class="text-grey-4 text-h6">
                  Call Logs
                </q-item-section>
              </q-item>
              <br>
              <q-item clickable v-ripple>
                <q-item-section class="text-white" avatar>
                  <q-icon name="account_box"></q-icon>
                </q-item-section>

                <q-item-section class="text-grey-4 text-h6">
                  Calls
                </q-item-section>
              </q-item>
              <br>
              <q-item class="text-white" clickable v-ripple>
                <q-item-section avatar>
                  <q-icon name="equalizer"></q-icon>
                </q-item-section>

                <q-item-section class="text-grey-4 text-h6">
                  Leads
                </q-item-section>
              </q-item>
              <br>
              <q-item class="text-white" clickable v-ripple>
                <q-item-section avatar>
                  <q-icon name="fact_check"></q-icon>
                </q-item-section>

                <q-item-section class="text-grey-4 text-h6">
                  Follow Up
                </q-item-section>
              </q-item>
            </q-list>
          </q-scroll-area>

          <!--
            in this case, we use a button (can be anything)
            so that user can switch back
            to mini-mode
          -->
          <div class="q-mini-drawer absolute" style="top: 50px; right: -19px">
            <q-btn
              dense
              round
              unelevated
              class="text-blue"
              color="white"
              :icon="miniState ? 'chevron_right' : 'chevron_left'"
              @click="toggleMiniState"
            ></q-btn> 
          </div>
        </q-drawer>
        <div class="lt-sm q-my-lg">
          <div class="row justify-around items-center">
            <div class="col-4 text-h5 text-weight-bold text-blue-grey-9">Telecalling</div>
            <div class="col-4">
              <div class="column items-end">
                <div class="col">
                  <q-item>
                    <q-item-section  style="text-align: end;">
                      <div class="text-weight-bold">DeadPool</div>
                      <div>User</div>
                    </q-item-section>
                    <q-item-section side avatar>
                      <q-avatar class="bg-grey"/>
                    </q-item-section>
                  </q-item>
                </div>
              </div>
            </div>
          </div>
        </div>

        <q-page-container>
          <router-view />
        </q-page-container>
      </q-layout>
    </div>
  </div>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  setup () {
    const drawer = ref(false)
    const miniState = ref(false)
    const toggleMiniState = () => {
        miniState.value = !miniState.value
      }
    const miniDrawerIcon = computed(() => {
      return miniState.value ? 'chevron_right' : 'chevron_left'
    })
    const drawerClick = (e) => {
        if (miniState.value) {
          miniState.value = false
          e.stopPropagation()
        }
      }

    return {
        drawer,
        miniState,
        toggleMiniState,
        drawerClick,
        miniDrawerIcon
    }
  }
}
</script>
<style>
*{
  /* color: white; */
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
 }
.iconHide {
  display: none;
  }
</style>