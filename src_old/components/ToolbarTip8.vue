

<script setup lang="ts">

import { ref , defineEmits, onMounted } from 'vue';
//import VueDatePicker from '@vuepic/vue-datepicker';
//import '@vuepic/vue-datepicker/dist/main.css'
import { CalendarIcon } from './@heroicons/vue/24/outline'
import { TrashIcon } from './@heroicons/vue/24/outline'
import { XMarkIcon } from './@heroicons/vue/24/outline'
import { Square2StackIcon } from './@heroicons/vue/24/outline'
import { RectangleGroupIcon  } from './@heroicons/vue/24/outline'
import { PlusIcon  } from './@heroicons/vue/24/outline'
import { MinusIcon  } from './@heroicons/vue/24/outline'
import { PencilSquareIcon  } from './@heroicons/vue/24/outline'
import { PaperAirplaneIcon  } from './@heroicons/vue/24/outline'
import { PaperClipIcon  } from './@heroicons/vue/24/outline'
import { ArrowPathIcon  } from './@heroicons/vue/24/outline'
import { ArrowUturnRightIcon  } from './@heroicons/vue/24/outline'
import { ArrowUturnLeftIcon  } from './@heroicons/vue/24/outline'
import { ArrowsPointingOutIcon  } from './@heroicons/vue/24/outline'
import { ArrowsPointingInIcon  } from './@heroicons/vue/24/outline'
import {  Cog6ToothIcon  } from './@heroicons/vue/24/outline'

import { EllipsisVerticalIcon } from './@heroicons/vue/24/outline'
import { EllipsisHorizontalIcon } from './@heroicons/vue/24/outline'
import { DocumentIcon } from './@heroicons/vue/24/outline'

import ToolbarItem8  from './ToolbarItem8.vue'
import ToolbarItemRadio8  from './ToolbarItemRadio8.vue'
import ToolbarItemSelect7  from './ToolbarItemSelect7.vue'



const props = defineProps(['toolbar_define' ,'icon_flat_mode']);


const emit = defineEmits(['toolbarItemClick', 
                           'toolbarItemToggle',
                           'toolbarItemSelect',
                           'toolbarItemSelectColor',
			   'toolbarItemRadio',

			   ]);
function toggle_handler( name , state ) {

      emit('toolbarItemToggle', name, state)
/*
      if ( radio ) {
        console.log("radio switch");
        for ( let i = 0; i < radioref.value.length ; i++) {
            console.log(radioref.value[i].radio_name());
            //console.log(radioref.value[i]);
       }
      }
*/

}
function radio_handler( radio_name, radio_index, name , state ) {

      emit('toolbarItemRadio', radio_name, radio_index,  name, state);

        console.log("radio switch",radio_name, radio_index,  name, state);
        for ( let i = 0; i < radioref.value.length ; i++) {
            console.log(radioref.value[i].radio_name());
	    if (radioref.value[i].radio_name() == radio_name ){
	        if (radioref.value[i].radio_index() != radio_index ) {
                      radioref.value[i].reset();
                }
	    }
            //console.log(radioref.value[i]);
       }

}
function click_handler( name ) {
      emit('toolbarItemClick', name)
}

function select_handler( name , data) {
      emit('toolbarItemSelect', name, data)
}
function select_color_handler( name , data) {
      emit('toolbarItemSelectColor', name, data)
}

onMounted(() => {
 // emit = defineEmits(props.handler_define)
});

const radioref = ref(null)

//const icon_flat_mode = false;


</script>


<template>
<div class="toolbar-base">

 <template v-for="item in props.toolbar_define" v-bind:key="item">
     <ToolbarItem8  v-if="!item.select && !item.radio" :tooltip="item.tooltip"  :name="item.name" :alignright="item.alignright" 
	                    @toolbarItemClick="click_handler"   
	                    @toolbarItemToggle="toggle_handler"  > 
		    <component v-bind:is="item.icon"   :class="{ icon : !props.icon_flat_mode , icon_flat : props.icon_flat_mode, leftspace : item.leftspace, toggle : item.toggle  }"/>
     </ToolbarItem8>
     <ToolbarItemRadio8  v-if="!item.select && item.radio" ref="radioref" :tooltip="item.tooltip"  :name="item.name" :alignright="item.alignright" 
	                    @toolbarItemClick="click_handler"   
	                    @toolbarItemToggle="toggle_handler" 
	                    @toolbarItemRadio="radio_handler" 
              :radio_name="item.radio_name"
              :radio_index="item.radio_index"
              :radio_class="item.radio_class"

			    > 
        <component v-bind:is="item.icon"  class="radioicon" :class="{ leftspace : item.leftspace, toggle : item.toggle, radio : item.radio  }"
	/>
     </ToolbarItemRadio8>
     <ToolbarItemSelect7  v-if="item.select" :tooltip="item.tooltip"  :name="item.name" :alignright="item.alignright" 
	                      > 
        <component v-bind:is="item.icon"  :name="item.name" :options="item.options" @toolbarItemSelect="select_handler" class="select" :class="{ leftspace : item.leftspace, toggle : item.toggle   }"/>
     </ToolbarItemSelect7>
</template>

	</div>
</template>

<style >

</style>

<style scoped>

.toolbar-base {
  display:flex;
  margin-left: 0px;
  margin-right: 0px;
  padding-left:10px;
  padding-right:10px;
  /* background-color: #f5f5f5;*/
}

.icon {
 width : 22px;
 height : 22px;
 cursor: pointer;
 /*margin: 3px 2px;*/
 margin: 3px 2px;
 padding: 3px 4px;
 box-shadow: 2px 2px 0px 0 lightgray;
}
 
.icon_flat {
 width : 22px;
 height : 22px;
 cursor: pointer;
 /*margin: 3px 2px;*/
 margin: 3px 2px;
 padding: 3px 4px;
 /*box-shadow: 2px 2px 0px 0 lightgray;*/
}

.radioicon {
 width : 22px;
 height : 22px;
 cursor: pointer;
 /*margin: 3px 2px;*/
 margin: 3px 2px;
 padding: 3px 4px;
/* box-shadow: 2px 2px 0px 0 lightgray;*/
}

.select  {
 margin: 3px 2px; 
/* margin: 3px 3px 0px 0px;*/
/* padding: 0px 0px;*/
  --vs-border: 0;
  --vs-border-radius: 0px;
  /* --vs-padding: 0px 8px;*/
  --vs-padding: 0px 4px;
  --vs-min-height: 28px;
  /*
  font-size: 15px;
  font-family: monospace;
  */
  --vs-font-family: inherit;
  box-shadow: 2px 2px 0px 0 lightgray;
}

.menu {
  font-family: monospace;
}

.menu-option {
  font-family: monospace;

}

.icon.mouse-down{
 box-shadow: -2px -2px 0px 0px lightgray;
}
.icon_flat.mouse-down{
 box-shadow: -2px -2px 0px 0px lightgray;
}

.radioicon.mouse-down{
 box-shadow: -2px -2px 0px 0px lightgray;
}

.leftspace {
 margin-left: 20px;

}
/*
.alignright{

  margin-left: auto;

}
*/
</style>
