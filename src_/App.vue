<script setup lang="ts">
//import HelloWorld from './components/HelloWorld.vue'
//import Toolbar from './components/Toolbar.vue'
//import ToolbarTip from './components/ToolbarTip.vue'
//import ToolbarTip2 from './components/ToolbarTip2.vue'
//import ToolbarTip3 from './components/ToolbarTip3.vue'
//import ToolbarTip4 from './components/ToolbarTip4.vue'
//import ToolbarTip5 from './components/ToolbarTip5.vue'
//import ToolbarTip6 from './components/ToolbarTip6.vue'
//import ToolbarTip7 from './components/ToolbarTip7.vue'
import ToolbarTip8 from './components/ToolbarTip8.vue'


//import { CalendarIcon } from './components/@heroicons/vue/24/outline'
import { CalendarIcon } from '@heroicons/vue/24/outline'
import { TrashIcon } from    '@heroicons/vue/24/outline'
import { XMarkIcon } from    '@heroicons/vue/24/outline'
import { Square2StackIcon } from       '@heroicons/vue/24/outline'
import { RectangleGroupIcon  } from    '@heroicons/vue/24/outline'
import { PlusIcon  } from              '@heroicons/vue/24/outline'
import { MinusIcon  } from             '@heroicons/vue/24/outline'
import { PencilSquareIcon  } from      '@heroicons/vue/24/outline'
import { PaperAirplaneIcon  } from     '@heroicons/vue/24/outline'
import { PaperClipIcon  } from         '@heroicons/vue/24/outline'
import { ArrowPathIcon  } from         '@heroicons/vue/24/outline'
import { ArrowUturnRightIcon  } from   '@heroicons/vue/24/outline'
import { ArrowUturnLeftIcon  } from    '@heroicons/vue/24/outline'
import { ArrowsPointingOutIcon  } from '@heroicons/vue/24/outline'
import { ArrowsPointingInIcon  } from  '@heroicons/vue/24/outline'
import { Cog6ToothIcon  } from         '@heroicons/vue/24/outline'

import { EllipsisVerticalIcon } from   '@heroicons/vue/24/outline'
import { EllipsisHorizontalIcon } from '@heroicons/vue/24/outline'
import { DocumentIcon } from           '@heroicons/vue/24/outline'

import Select from "./components/Select.vue";
//import Select2 from "./components/Select2.vue";
//import Select3 from "./components/Select3.vue";
//import Select4 from "./components/Select4.vue";
import SelectColor from "./components/SelectColor.vue";
import SelectEmoji from "./components/SelectEmoji.vue";

// https://tabler.io/icons
import { IconHome } from '@tabler/icons-vue';
import { IconMoodSmileBeam } from '@tabler/icons-vue';

/*
function clickA( data ) {

   console.log("*************** Click A:", data);
   //alert("Click A");
}

function clickB( data ) {

   console.log("*************** Click B:", data);
   //alert("Click B");
}

const handler_define = [
  "clickA",
  "clickB",
];
*/



const toolbar_define = [

{ icon : ArrowUturnRightIcon,
  name : "ArrowUturnRightIcon",
  handler : "clickA",
  tooltip : "A         OK",
},
{ icon : ArrowUturnLeftIcon,
  name : "ArrowUturnLeftIcon",
  tooltip : "B         OK",
  handler : "clickB",
},
{ icon : RectangleGroupIcon,
  name : "RectangleGroupIcon",
  tooltip : "B         OK",
},
{ icon : Square2StackIcon,
  name : "Square2StackIcon",
  tooltip : "B         OK",
},
{ icon : CalendarIcon,
  name : "CalendarIcon",
  leftspace : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  toggle : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  toggle : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  toggle : true,
  tooltip : "B         OK",
},
{ icon :XMarkIcon ,
  name : "XMarkIcon",
  tooltip : "B         OK",
},
{ icon : PlusIcon,
  name : "PlusIcon",
  tooltip : "B         OK",
},
{ icon : MinusIcon,
  name : "MinusIcon",
  tooltip : "B         OK",
},


{ icon : PencilSquareIcon,
  name : "PencilSquareIcon",
  leftspace: true,
  tooltip : "B         OK",
},

{ icon : PaperAirplaneIcon,
  name : "PaperAirplaneIcon",
  tooltip : "B         OK",
},
{ icon : PaperClipIcon,
  name : "PaperClipIcon",
  tooltip : "B         OK",
},

{ icon : Select,
  select: true,
  name : "Select2",
  options : [
      { label: 'Option #1a', value: 'option_1a' },
      { label: 'Option #2a', value: 'option_2a' },
      { label: 'Option #3a', value: 'option_3a' },
    ],

  tooltip : "Select         OK",
},
/*
{ icon : PaperAirplaneIcon,
  name : "PaperAirplaneIcon",
  tooltip : "B         OK",
},
*/
/*
{ icon : Select2,
  select: true,
  name : "Select2",
  tooltip : "Select         OK",
},

{ icon : Select3,
  select: true,
  name : "Select3",
  tooltip : "Select         OK",
},
{ icon : Select4,
  select: true,
  name : "Select4",
  tooltip : "Select         OK",
},
*/
{ icon : SelectColor,
  select: true,
  name : "SelectColor2",
  options : [
      { label: 'Option #1a', value: 'option_1a' },
      { label: 'Option #2a', value: 'option_2a' },
      { label: 'Option #3a', value: 'option_3a' },
    ],
  tooltip : "Select      OK",
},
{ icon : SelectEmoji,
  select: true,
  name : "SelectEmoji",
  options : [
      { label: 'Option #1a', value: 'option_1a' },
      { label: 'Option #2a', value: 'option_2a' },
      { label: 'Option #3a', value: 'option_3a' },
    ],
  tooltip : "Select      OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  radio : true,
  radio_name : "onsen",
  radio_index : 1,
  radio_class : "start",
  toggle : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  radio : true,
  radio_name : "onsen",
  radio_index : 2,
  radio_class : "mid",
  toggle : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  radio : true,
  radio_name : "onsen",
  radio_index : 3,
  radio_class : "mid",
  toggle : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  radio : true,
  radio_name : "onsen",
  radio_index : 4,
  radio_class : "end",
  toggle : true,
  tooltip : "B         OK",
},

{ icon : TrashIcon,
  name : "TrashIcon",
  radio : true,
  radio_name : "yama",
  radio_index : 1,
  radio_class : "start",
  toggle : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  radio : true,
  radio_name : "yama",
  radio_index : 2,
  radio_class : "mid",
  toggle : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  radio : true,
  radio_name : "yama",
  radio_index : 3,
  radio_class : "end",
  toggle : true,
  tooltip : "B         OK",
},

{ icon : IconHome ,
  name : "IconHome",
  tooltip : "B         OK",
},
{ icon : IconMoodSmileBeam ,
  name : "IconMoodSmileBeam",
  tooltip : "B         OK",
},

/*
  <ArrowsPointingOutIcon class="icon" />
  <ArrowsPointingInIcon class="icon" />
  <ArrowPathIcon class="icon" />
  <DocumentIcon class="icon" />
*/

{ icon : EllipsisVerticalIcon,
  name : "EllipsisVerticalIcon",
  alignright: true,
  tooltip : "B         OK",
},
{ icon : EllipsisHorizontalIcon,
  name : "EllipsisHorizontalIcon",
  tooltip : "B         OK",
},
{ icon : Cog6ToothIcon,
  name : "Cog6ToothIcon",
  tooltip : "B         OK",
},
];

function toolbarItemClick(data) {
  console.log(" App toolbar click:", data);


}
function toolbarItemToggle(data, state) {
  console.log(" App toolbar toggle:", data, state);
}

function toolbarItemSelect(name, data) {
  console.log(" App toolbar select:", name, data);
}

function toolbarItemSelectColor(name, data) {
  console.log(" App toolbar select color:", name, data);
}

function toolbarItemRadio(radio_name, radio_index,  name, state) {

  console.log(" App toolbar Radio:", radio_name, radio_index, state);

}
</script>

<template>
<!--
<div>
	<p> "Toolbar" toolbar</p>
  <Toolbar />
</div>
-->
<!--
<div>
	<p> "ToolbarTip" tooltip and emit</p>
  <ToolbarTip />
</div>

<div>
	<p> "ToolbarTip2" dynamic item</p>
  <ToolbarTip2 />
</div>

<div>
	<p> "ToolbarTip3" for dynamic item</p>
  <ToolbarTip3 :toolbar_define="toolbar_define"  @toolbarItemClick="toolbarItemClick" />
</div>

<div>
	<p> "ToolbarTip4" for dynamic item  leftspace & toggle </p>
  <ToolbarTip4 :toolbar_define="toolbar_define"  @toolbarItemClick="toolbarItemClick" />
</div>

<div>
	<p> "ToolbarTip5" for dynamic item  leftspace & toggle  & align right</p>
  <ToolbarTip5 :toolbar_define="toolbar_define"  @toolbarItemClick="toolbarItemClick" />
</div>
-->
<!--
<div>
	<p> "ToolbarTip6" hundler update</p>
  <ToolbarTip6 :toolbar_define="toolbar_define"  
		                                 @toolbarItemClick="toolbarItemClick"  
		                                 @toolbarItemToggle="toolbarItemToggle"  
						 />
</div>
<div>
	<p> "ToolbarTip7" select menu</p>
  <ToolbarTip7 :toolbar_define="toolbar_define"  
		                                 @toolbarItemClick="toolbarItemClick"  
		                                 @toolbarItemToggle="toolbarItemToggle"  
		                                 @toolbarItemSelect="toolbarItemSelect"  
						 />
</div>
-->
<div>
	<p> "ToolbarTip8" radio button</p>
  <ToolbarTip8 :toolbar_define="toolbar_define"  
		                                 @toolbarItemClick="toolbarItemClick"  
		                                 @toolbarItemToggle="toolbarItemToggle"  
		                                 @toolbarItemSelect="toolbarItemSelect"  
		                                 @toolbarItemRadio="toolbarItemRadio"
						 />
</div>
<div>
	<p> "ToolbarTip8" radio button icon_flat</p>
  <ToolbarTip8 :toolbar_define="toolbar_define"  :icon_flat_mode="true"
		                                 @toolbarItemClick="toolbarItemClick"  
		                                 @toolbarItemToggle="toolbarItemToggle"  
		                                 @toolbarItemSelect="toolbarItemSelect"  
		                                 @toolbarItemRadio="toolbarItemRadio"
						 />
</div>
</template>

<style scoped>
</style>
