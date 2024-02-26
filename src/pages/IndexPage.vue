<template>
  <q-page>
    <div class="example-row-horizontal-alignment">
      <div class="row justify-center q-pa-md">
        <div class="col-6 text-h5">
          Follow Up
        </div>
        <div class="col-6">
         <div class="column items-end">
          <div class="col">
            <q-btn-dropdown class="bg-pink-1 text-pink-9" label="Expired">
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
      <div>
        <q-list class="example-row-stacked-to-horizontal">
          <div class="row">
            <div v-for="(cd, index) in contactDetails" :key="index" class="col-12 col-lg-4 contact-hover q-pa-sm" @click="openDialog(cd)">
              <div class="column items-center">
                <div class="col">
                  <q-item chatWidth>
                    <q-item-section avatar class="self-start">
                      <q-avatar  color="primary">
                          <img :src="cd.img" width="75px" height="75px">
                      </q-avatar>
                    </q-item-section>

                    <q-item-section>
                      <p>{{cd.number}}<br>
                      {{ cd.name }}</p>
                    </q-item-section>

                    <q-item-section side>
                      <p>{{cd.mail}}<br>
                      {{cd.course}}</p>
                    </q-item-section>
                  </q-item>
                </div>
              </div>
            </div>
          </div>
          <q-dialog v-model="icon">
            <q-card>
              <q-card-section class="row">
                <div class="text-h6">
                  <q-item>
                    <q-item-section avatar>
                      <q-avatar color="primary">
                        <img :src="selectedItem.img" width="75px" height="75px">
                      </q-avatar>
                    </q-item-section>

                    <q-item-section>
                      <div class="text-h4 text-weight-bold">{{ selectedItem.name }}</div>
                      <div>{{ selectedItem.number }}</div>
                    </q-item-section>
                  </q-item>
                </div>
                <q-space />
                <q-btn icon="close" flat v-close-popup />
              </q-card-section>

              <q-card-section class="row">
                
                <q-expansion-item
                  default-opened
                  label="Contact Details"
                  class="col-12 col-sm-6"
                  style="color: rgb(144, 145, 145);"
                >
                  <q-item>
                    <q-item-section class="text-black">
                      {{ selectedItem.mail }}
                    </q-item-section>
                    
                    <q-item-section side>
                      <span class="material-symbols-outlined text-blue">mail</span>                    </q-item-section>
                  </q-item>
                  <q-item>
                    <q-item-section class="text-black">
                      {{selectedItem.number}}
                    </q-item-section>
                    
                    <q-item-section side>
                      <span class="material-symbols-outlined text-blue">call</span>                    </q-item-section>
                  </q-item>
                </q-expansion-item>    
                <q-expansion-item
                  default-opened
                  label="Course Details"
                  class="col-12 col-sm-6"
                  style="color: rgb(144, 145, 145);"
                >
                  <q-item>
                    <q-item-section class="text-black">
                      {{ selectedItem.course }}
                    </q-item-section>
                        
                    <q-item-section side>
                      <span class="material-symbols-outlined text-blue">laptop_chromebook</span>                    </q-item-section>
                  </q-item>
                  <q-item>
                    <q-item-section class="text-black">
                      {{selectedItem.mode}}
                    </q-item-section>
                    
                    <q-item-section side>
                      <span class="material-symbols-outlined text-blue">cloud_off</span>                    </q-item-section>
                  </q-item>
                </q-expansion-item> 
                <q-expansion-item
                  default-opened
                  label="Follow Up Details"
                  class="col-12 col-sm-6"
                  style="color: rgb(144, 145, 145);"
                >
                  <q-item>
                    <q-item-section class="text-black">
                      {{selectedItem.date}}
                    </q-item-section>
                        
                    <q-item-section side>
                      <span class="material-symbols-outlined text-blue">calendar_month</span>                    </q-item-section>
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
              const icon = ref(false)
              const selectedItem = ref({})
              const contactDetails = [
                    {
                        img:'https://www.myfreetextures.com/wp-content/uploads/2014/11/flowing-blue-abstract-texture.jpg',
                        number:'+91 5263987741',
                        name:'Selina',
                        mail:'batman123@gmail.com',
                        course:'Full Stack Developer',
                        date:'10-02-2024',
                        mode:'Offline'
                    },
                    {
                        img:'https://www.myfreetextures.com/wp-content/uploads/2014/11/flowing-blue-abstract-texture.jpg',
                        number:'+91 5263987741',
                        name:'Luciya',
                        mail:'batman123@gmail.com',
                        course:'Full Stack Developer',
                        date:'14-12-2000',
                        mode:'Offline'
                    },
                    {
                        img:'https://www.myfreetextures.com/wp-content/uploads/2014/11/flowing-blue-abstract-texture.jpg',
                        number:'+91 5263987741',
                        name:'Beulah',
                        mail:'batman123@gmail.com',
                        course:'Full Stack Developer',
                        date:'10-05-2023',
                        mode:'Offline'
                    },
                    {
                        img:'https://www.myfreetextures.com/wp-content/uploads/2014/11/flowing-blue-abstract-texture.jpg',
                        number:'+91 5263987741',
                        name:'Jothi',
                        mail:'batman123@gmail.com',
                        course:'Full Stack Developer',
                        date:'19-06-2024',
                        mode:'Offline'
                    },
                    {
                        img:'https://www.myfreetextures.com/wp-content/uploads/2014/11/flowing-blue-abstract-texture.jpg',
                        number:'+91 5263987741',
                        name:'Stephen',
                        mail:'batman123@gmail.com',
                        course:'Full Stack Developer',
                        date:'10-02-2000',
                        mode:'Offline'
                    },
                ]
                const openDialog = (item) => {
                selectedItem.value = item
                icon.value = true
                }
                return {
                  onItemClick () {
                  },
                  icon,
                  selectedItem,
                  contactDetails,
                  openDialog
            
                  
                }
  }
})
</script>

