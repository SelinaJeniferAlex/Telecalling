<template>
  <q-page container class="q-pt-lg">
    <div class="example-row-horizontal-alignment">
      <div class="row justify-around">
        <div class="col-4 col-xl-4 text-h5 text-blue-grey-9">Follow Up</div>
        <div class="col-4 col-xl-4">
         <div class="column items-end">
          <div class="col">
            <q-btn-dropdown class="bg-pink-2 text-pink-9" label="Expired">
              <q-list>
                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Photos</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Videos</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>Articles</q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
            </q-btn-dropdown>
          </div>
         </div>
        </div>
      </div>
    </div>
    <div class="q-my-md">
      <div class="example-row-horizontal-alignment q-py-md">
        <q-list class="row justify-around">
          <div class="col-12 col-md-10 col-lg-4 contact-hover" @click="icon=true">
            <q-item class="avatar-position" style="max-width: 400px;">
              <q-item-section avatar>
                <q-avatar  color="primary"/>
              </q-item-section>

              <q-item-section>
                <p>+91&nbsp;5263987741<br>
                Batman</p>
              </q-item-section>

              <q-item-section side>
                <p>batman123@gmail.com<br>
                Full Stack Developer</p>
              </q-item-section>
            </q-item>
          </div>
          <div class="col-12 col-md-10 col-lg-4 contact-hover" @click="icon=true">
            <q-item style="max-width: 400px;">
              <q-item-section avatar>
                <q-avatar color="primary"/>
              </q-item-section>

              <q-item-section>
                <p>+91&nbsp;5263987741<br>
                Batman</p>
              </q-item-section>

              <q-item-section side>
                <p>batman123@gmail.com<br>
                Full Stack Developer</p>
              </q-item-section>
            </q-item>
          </div>
          <q-dialog v-model="icon">
            <q-card>
              <q-card-section class="row">
                <div class="text-h6">
                  <q-item>
                    <q-item-section avatar>
                      <q-avatar color="primary"/>
                    </q-item-section>

                    <q-item-section>
                      <div class="text-h4 text-weight-bold">Batman</div>
                      <div>+91&nbsp;5263987741</div>
                    </q-item-section>
                  </q-item>
                </div>
                <q-space />
                <q-btn icon="close" flat round dense v-close-popup />
              </q-card-section>

              <q-card-section class="row">
                
                <q-expansion-item
                  default-opened
                  label="Contact Details"
                  class="col-12 col-sm-6"
                >
                  <q-item>
                    <q-item-section>
                      batman123@gmail.com
                    </q-item-section>
                    
                    <q-item-section side>
                      <q-icon name="email" color="blue" />
                    </q-item-section>
                  </q-item>
                  <q-item>
                    <q-item-section>
                      +91&nbsp;5263987741
                    </q-item-section>
                    
                    <q-item-section side>
                      <q-icon name="phone" color="blue" />
                    </q-item-section>
                  </q-item>
                </q-expansion-item>    
                <q-expansion-item
                  default-opened
                  label="Course Details"
                  class="col-12 col-sm-6"
                >
                  <q-item>
                    <q-item-section>
                      Full Stack Developer
                    </q-item-section>
                        
                    <q-item-section side>
                      <q-icon name="book" color="blue"/>
                    </q-item-section>
                  </q-item>
                  <q-item>
                    <q-item-section>
                      Offline
                    </q-item-section>
                    
                    <q-item-section side>
                      <q-icon name="cloud" color="blue"/>
                    </q-item-section>
                  </q-item>
                </q-expansion-item> 
                <q-expansion-item
                  default-opened
                  label="Follow Up Details"
                  class="col-12 col-sm-6"
                >
                  <q-item>
                    <q-item-section>
                      10-02-2023
                    </q-item-section>
                        
                    <q-item-section side>
                      <q-icon name="calendar" color="blue"/>
                    </q-item-section>
                  </q-item>
                </q-expansion-item>           
              </q-card-section>
            </q-card>
          </q-dialog>
          
        </q-list>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import { ref } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  setup () {
    return {
      onItemClick () {
      },
      icon: ref(false),
    }
  }
})
</script>
