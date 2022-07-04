<template>
  <div>
    <q-layout view="lHh Lpr lff" style="height:300px">
      <q-header unelevated class="bg-grey-2">
        <q-toolbar>
           <q-btn unelevated flat text-color="dark" color="white" icon="animation" label="animate" />
           <q-separator white vertical inset />
          <q-btn class="bg-grey-2 text-black" stretch flat icon="schedule" label="5.0s" />
        </q-toolbar>
      </q-header>

      <q-drawer
        v-model="drawer"
        show-if-above
        :mini="!drawer || miniState"
        @click.capture="drawerClick"
        :width="450"
        :breakpoint="500"
        bordered
        class="bg-black"
      >
        <q-scroll-area class="fit" >
         
    <q-splitter
      v-model="splitterModel"
    >
      <template v-slot:before>  
        <q-tabs
          v-model="tab"
          vertical
          class="text-grey-4"
        >
          <q-tab name="view_quilt" icon="view_quilt" label="Templates" />
          <q-tab name="interests" icon="interests" label="Elements" />
          <q-tab name="cloud_upload" icon="cloud_upload" label="Uploads" />
          <q-tab name="text_format" icon="text_format" label="Text" />
          <q-tab name="photo_camera" icon="photo_camera" label="Photos" />
          <q-tab name="more_horiz" icon="more_horiz" label="More" />
        </q-tabs>
      </template>

      <template v-slot:after>
        <q-tab-panels
          v-model="tab"
          animated
          swipeable
          vertical
          transition-prev="jump-up"
          transition-next="jump-up"
          class="tab-bg text-white"
        >
          <q-tab-panel name="view_quilt">
              <!-- <q-toolbar class="bg-white text-white rounded-borders">      
                <q-input filled borderless label="Search 1080p templates" v-model="text">
                  <template v-slot:prepend>
                    <q-icon v-if="text === '' " name="search" />
                    <q-icon v-else name="clear" class="cursor-pointer" @click="text = ''" />
                  </template>
                </q-input>
                <q-space />
                <q-btn round dense flat icon="tune" color="black" />
            </q-toolbar> -->
              
            <div class="q-gutter-y-md column" style="width: 320px; max-width: 100%">
              <q-input filled class="bg-white text-black rounded-borders" color="black" outlined v-model="text" label="Search 1080p templates">
                <template v-slot:prepend>
                  <q-icon name="search" />
                </template>
                <template v-slot:append>
                  <q-btn round dense flat icon="tune" />
                </template>
              </q-input>
            </div>

          <q-space /> 

              <div class="q-mt-md" style="max-width:320px;">
                <q-tabs
                  v-model="tab"
                  inline-label
                  outside-arrows
                  mobile-arrows
                  class="tabs-styled"
                >
                  <!-- <q-tab name="Intro" style="background: #414243; color: #B4B5B5; border-radius:10px;" label="Intro" /> -->
                  <q-tab name="Intro"  label="Intro" />
                  <q-tab name="alarms" label="Thank you" />
                  <q-tab name="movies" label="Nature" />
                  <q-tab name="photos" label="Photos" />
                  <q-tab name="videos" label="Birthday" />
                  <q-tab name="addressbook" label="Business" />
                </q-tabs>
              </div>

            <q-space />

            <div class="card-container">
              <div class="card-row">
                <div class="card-item">
                  <q-video src="https://www.youtube.com/embed/kOkQ4T5WO9E" />
                </div>
                <div class="card-item">
                  <q-video src="https://www.youtube.com/embed/k3_tw44QsZQ?rel=0" />
                </div>
              </div>

              <q-space />
              
              <div class="card-row">
                 <div class="card-item">
                  <q-video src="https://www.youtube.com/embed/k3_tw44QsZQ?rel=0" />
                 </div>
                <div class="card-item">
                  <q-video src="https://www.youtube.com/embed/kOkQ4T5WO9E" />
                </div>
              </div>
              
              <q-space />
              
              <div class="card-row">
                 <div class="card-item">
                    <q-video src="https://www.youtube.com/embed/kOkQ4T5WO9E" />
                 </div>
                <div class="card-item">
                   <q-video src="https://www.youtube.com/embed/k3_tw44QsZQ" />
                </div>
              </div>

              <q-space />

                <div class="card-row">
                 <div class="card-item">
                     <q-video src="https://www.youtube.com/embed/k3_tw44QsZQ" />
                 </div>
                <div class="card-item">
                  <q-video src="https://www.youtube.com/embed/kOkQ4T5WO9E" />
                </div>
              </div>
            </div>
            
          <q-space />
          </q-tab-panel>

          <q-tab-panel name="interests">
             <div class="q-gutter-y-md column">
              <q-input v-model="text" label="Search anything in canva" class="bg-white text-black rounded-borders" outlined filled>
                <template v-slot:prepend>
                  <q-icon name="search" />
                </template>
              </q-input>
              
              </div>
            <div class="text-h4 q-mb-md">Elements</div>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
          </q-tab-panel>

          <q-tab-panel name="cloud_upload">
            <div class="text-h4 q-mb-md">Uploads</div>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
          </q-tab-panel>

          <q-tab-panel name="text_format">
            <div class="text-h4 q-mb-md">Text</div>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
          </q-tab-panel>

          <q-tab-panel name="photo_camera">
            <div class="text-h4 q-mb-md">Photos</div>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
          </q-tab-panel>

          <q-tab-panel name="more_horiz">
            <div class="text-h4 q-mb-md">More</div>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
          </q-tab-panel>
        </q-tab-panels>
      </template>

    </q-splitter>
  
        </q-scroll-area>

        <!--
          in this case, we use a button (can be anything)
          so that user can switch back
          to mini-mode
        -->
        <div class="q-mini-drawer-hide absolute" style="top: 20em; right: -17px">
          <q-btn
            dense
            round
            unelevated
            color="black"
            icon="chevron_left"
            @click="miniState = true"
          />
        </div>
      </q-drawer>
<!-- page container -->
      <q-page-container class="bg-grey-4 text-black">
        <q-page class="my-card"> 
           <div class="row add-duplicate-icon">
              <q-btn round flat class="bg-grey-4 text-grey" icon="queue" />
              <q-btn round flat class="bg-grey-4 text-grey" icon="post_add" />
           </div>

          <div class="row">
            <div class="page-sheet">
            </div>
            
            <div class="add-comment-btn">
               <q-btn round color="grey" class="bg-grey-1 text-grey-9" icon="maps_ugc" />
            </div>
          </div>
          
          <div class="page-button">
              <q-btn flat class="bg-grey-5 full-width" icon="add" label="Add Page" />
          </div>
          </q-page>
          
      </q-page-container>
      
      <q-footer class="bg-grey-2 text-black">
        <div class="q-mini-drawer-hide absolute" style="top: -15px; right: 500px;">
          <q-btn
            dense
            round
            unelevated
            color="white"
            text-color="black"
            icon="expand_less"
            @click="miniState = true"
          />
        </div>
        <q-toolbar>
          <q-btn class="bg-grey-2 text-black" flat icon="edit_note" label="Notes" />
          <q-toolbar-title class="toolbar-title">0:00/0:05</q-toolbar-title>
           <q-space />
           <q-separator dark vertical />
            <q-slider 
              label-always 
              v-model="standard" 
              :min="0" :max="100"  
              label
              :label-value="'Zoom: ' + standard"
              class="slider" color="black" />
            <q-separator dark vertical />
            <q-btn stretch flat icon="zoom_out_map" />
            <q-separator dark vertical />
            <q-btn stretch flat icon="filter_1" />
            <q-separator dark vertical />
            <q-btn stretch flat icon="open_in_full" />
            <!-- <q-separator white vertical inset />
            <q-btn stretch flat icon="help_outline" /> -->
        </q-toolbar>
    </q-footer>

    </q-layout>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const miniState = ref(false)

    return {
      drawer: ref(false),
      miniState,

      drawerClick (e) {
        // if in "mini" state and user
        // click on drawer, we switch it to "normal" mode
        if (miniState.value) {
          miniState.value = false

          // notice we have registered an event with capture flag;
          // we need to stop further propagation as this click is
          // intended for switching drawer to "normal" mode only
          e.stopPropagation()
        }
      },
      text: ref(''),
      standard: ref(2),
    }
  }
}
</script>

<style scoped>
  .tab-bg {
    background-color: #18191B;
  }
  .tabs-styled {
    background-color:#252627;
    border-radius: 5px;
    /* border: 1px solid #252627; */
  }

 .card-container {
    width: 320px;
    padding-top: 0.5rem;
    /* background-color: red; */
}
.card-row {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-evenly;
    /* padding: 2rem; */
    padding-bottom: 2rem;
    /* background-color: brown; */
}
.card-item {
    height: 120px; 
    flex-basis: 48%; 
    background-color: rgb(181, 178, 178);
    /* width: 50rem;  */
    /* margin: 0.1rem; */
}
.slider {
  width: 30%;
}
.toolbar-title {
  font-size: 16px;
}
.my-card {
  /* margin-top: 1rem; */
  margin-left: 10rem;
  margin-right: 10rem;
  padding: 7rem;
  /* width: 50%; */
  height: 30%;
  /* background-color: red; */
}
.page-sheet {
  width: 300px;
  height: 150px;
  background-color: #ffffff;
  margin-bottom: 20px;
}
.page-button {
  width: 300px;
}
.add-comment-btn {
  padding-left: 10px;
}
.add-duplicate-icon {
  margin-left: 14rem;
}
</style>