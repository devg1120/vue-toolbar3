<script setup lang="ts">
import ToolbarTip8 from "./components/ToolbarTip8.vue";
import { CalendarIcon } from "@heroicons/vue/24/outline";
import { TrashIcon } from "@heroicons/vue/24/outline";
import { XMarkIcon } from "@heroicons/vue/24/outline";
import { Square2StackIcon } from "@heroicons/vue/24/outline";
import { RectangleGroupIcon } from "@heroicons/vue/24/outline";
import { PlusIcon } from "@heroicons/vue/24/outline";
import { MinusIcon } from "@heroicons/vue/24/outline";
import { PencilSquareIcon } from "@heroicons/vue/24/outline";
import { PaperAirplaneIcon } from "@heroicons/vue/24/outline";
import { PaperClipIcon } from "@heroicons/vue/24/outline";
import { ArrowPathIcon } from "@heroicons/vue/24/outline";
import { ArrowUturnRightIcon } from "@heroicons/vue/24/outline";
import { ArrowUturnLeftIcon } from "@heroicons/vue/24/outline";
import { ArrowsPointingOutIcon } from "@heroicons/vue/24/outline";
import { ArrowsPointingInIcon } from "@heroicons/vue/24/outline";
import { Cog6ToothIcon } from "@heroicons/vue/24/outline";

import { EllipsisVerticalIcon } from "@heroicons/vue/24/outline";
import { EllipsisHorizontalIcon } from "@heroicons/vue/24/outline";
import { DocumentIcon } from "@heroicons/vue/24/outline";

import Select from "./components/Select.vue";
import SelectColor from "./components/SelectColor.vue";
import SelectEmoji from "./components/SelectEmoji.vue";

// https://tabler.io/icons
import { IconHome } from "@tabler/icons-vue";
import { IconMoodSmileBeam } from "@tabler/icons-vue";
//tallymark-1
import {  IconTallymark1 } from "@tabler/icons-vue";

/*
<svg  xmlns="http://www.w3.org/2000/svg"  width="24"  height="24"  viewBox="0 0 24 24"  fill="none"  stroke="currentColor"  stroke-width="2"  stroke-linecap="round"  stroke-linejoin="round"  class="icon icon-tabler icons-tabler-outline icon-tabler-minus-vertical"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M12 5v14" /></svg>
*/

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
  {
    //icon: ArrowUturnRightIcon,
    icon: IconTallymark1,
    name: "ArrowUturnRightIcon",
    handler: "clickA",
    tooltip: "A         OK",
  },
  {
    icon: ArrowUturnLeftIcon,
    name: "ArrowUturnLeftIcon",
    tooltip: "B         OK",
    handler: "clickB",
  },
  {
    icon: RectangleGroupIcon,
    name: "RectangleGroupIcon",
    tooltip: "B         OK",
  },
  { icon: Square2StackIcon, name: "Square2StackIcon", tooltip: "B         OK" },
  {
    icon: CalendarIcon,
    name: "CalendarIcon",
    leftspace: true,
    tooltip: "B         OK",
  },
  { icon: TrashIcon, name: "TrashIcon", toggle: true, leftspace: true, tooltip: "B         OK" },
  { icon: TrashIcon, name: "TrashIcon", toggle: true, tooltip: "B         OK" },
  { icon: TrashIcon, name: "TrashIcon", toggle: true, tooltip: "B         OK" },
  { icon: XMarkIcon, name: "XMarkIcon", tooltip: "B         OK" },
  { icon: PlusIcon, name: "PlusIcon", tooltip: "B         OK" },
  { icon: MinusIcon, name: "MinusIcon", tooltip: "B         OK" },

  {
    icon: PencilSquareIcon,
    name: "PencilSquareIcon",
    leftspace: true,
    tooltip: "B         OK",
  },

  {
    icon: PaperAirplaneIcon,
    name: "PaperAirplaneIcon",
    tooltip: "B         OK",
  },
  { icon: PaperClipIcon, name: "PaperClipIcon", tooltip: "B         OK" },

  {
    icon: Select,
    select: true,
    name: "Select2",
    options: [
      { label: "Option #1a", value: "option_1a" },
      { label: "Option #2a", value: "option_2a" },
      { label: "Option #3a", value: "option_3a" },
    ],

    tooltip: "Select         OK",
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
  {
    icon: SelectColor,
    select: true,
    name: "SelectColor2",
    options: [
      { label: "Option #1a", value: "option_1a" },
      { label: "Option #2a", value: "option_2a" },
      { label: "Option #3a", value: "option_3a" },
    ],
    tooltip: "Select      OK",
  },
  {
    icon: SelectEmoji,
    select: true,
    name: "SelectEmoji",
    options: [
      { label: "Option #1a", value: "option_1a" },
      { label: "Option #2a", value: "option_2a" },
      { label: "Option #3a", value: "option_3a" },
    ],
    tooltip: "Select      OK",
  },
  {
    icon: TrashIcon,
    name: "TrashIcon",
    radio: true,
    radio_name: "onsen",
    radio_index: 1,
    radio_class: "start",
    toggle: true,
    tooltip: "B         OK",
  },
  {
    icon: TrashIcon,
    name: "TrashIcon",
    radio: true,
    radio_name: "onsen",
    radio_index: 2,
    radio_class: "mid",
    toggle: true,
    tooltip: "B         OK",
  },
  {
    icon: TrashIcon,
    name: "TrashIcon",
    radio: true,
    radio_name: "onsen",
    radio_index: 3,
    radio_class: "mid",
    toggle: true,
    tooltip: "B         OK",
  },
  {
    icon: TrashIcon,
    name: "TrashIcon",
    radio: true,
    radio_name: "onsen",
    radio_index: 4,
    radio_class: "end",
    toggle: true,
    tooltip: "B         OK",
  },

  {
    icon: TrashIcon,
    name: "TrashIcon",
    radio: true,
    radio_name: "yama",
    radio_index: 1,
    radio_class: "start",
    toggle: true,
    tooltip: "B         OK",
  },
  {
    icon: TrashIcon,
    name: "TrashIcon",
    radio: true,
    radio_name: "yama",
    radio_index: 2,
    radio_class: "mid",
    toggle: true,
    tooltip: "B         OK",
  },
  {
    icon: TrashIcon,
    name: "TrashIcon",
    radio: true,
    radio_name: "yama",
    radio_index: 3,
    radio_class: "end",
    toggle: true,
    tooltip: "B         OK",
  },

  { icon: IconHome, name: "IconHome", tooltip: "B         OK" },
  {
    icon: IconMoodSmileBeam,
    name: "IconMoodSmileBeam",
    tooltip: "B         OK",
  },

  /*
  <ArrowsPointingOutIcon class="icon" />
  <ArrowsPointingInIcon class="icon" />
  <ArrowPathIcon class="icon" />
  <DocumentIcon class="icon" />
*/

  {
    icon: EllipsisVerticalIcon,
    name: "EllipsisVerticalIcon",
    alignright: true,
    tooltip: "B         OK",
  },
  {
    icon: EllipsisHorizontalIcon,
    name: "EllipsisHorizontalIcon",
    tooltip: "B         OK",
  },
  { icon: Cog6ToothIcon, name: "Cog6ToothIcon", tooltip: "B         OK" },
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

function toolbarItemRadio(radio_name, radio_index, name, state) {
  console.log(" App toolbar Radio:", radio_name, radio_index, state);
}
</script>

<template>
  <div>
    <p>"ToolbarTip8" radio button</p>
    <ToolbarTip8
      :toolbar_define="toolbar_define"
      @toolbarItemClick="toolbarItemClick"
      @toolbarItemToggle="toolbarItemToggle"
      @toolbarItemSelect="toolbarItemSelect"
      @toolbarItemRadio="toolbarItemRadio"
    />
  </div>
  <div>
    <p>"ToolbarTip8" radio button icon_flat</p>
    <ToolbarTip8
      :toolbar_define="toolbar_define"
      :icon_flat_mode="true"
      @toolbarItemClick="toolbarItemClick"
      @toolbarItemToggle="toolbarItemToggle"
      @toolbarItemSelect="toolbarItemSelect"
      @toolbarItemRadio="toolbarItemRadio"
    />
  </div>
</template>

<style scoped></style>
