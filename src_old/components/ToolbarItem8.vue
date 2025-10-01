<script setup lang="ts">

import { ref , defineProps, defineEmits, onMounted, useTemplateRef} from 'vue';

const props = defineProps(['tooltip', 'name','alignright']);


const emit = defineEmits(['toolbarItemClick', 'toolbarItemToggle']);
const item  = useTemplateRef('item')

function item_mousedown(e) {
      emit('toolbarItemClick', props.name)
}
function item_mouseup(e) {
}

function item_toggle_switch(e, state) {
      emit('toolbarItemToggle', props.name, state )
}

onMounted(() => {
     let icons = item.value.querySelectorAll(".icon")
     if (icons.length == 0) {
         icons = item.value.querySelectorAll(".icon_flat")
     }
     icons.forEach((icon) => {
        // マウスオーバーで表示する
       icon.addEventListener("mouseover", function () {
           const targetIcon = this
           const activeTooltip = targetIcon.parentElement.nextElementSibling
           activeTooltip.classList.add("tip_active")
       });
        // マウスが外れたら非表示にする
       icon.addEventListener("mouseout", function () {
           const targetIcon = this
           const activeTooltip = targetIcon.parentElement.nextElementSibling
           activeTooltip.classList.remove("tip_active")
       });
       //icon.addEventListener("mousedown", item_mousedown) ;
       //icon.addEventListener("mouseup", item_mouseup);
       icon.addEventListener("mousedown", function (e) {
           const targetIcon = this
           //const icon = targetIcon.parentElement
	   if (targetIcon.classList.contains("toggle")) {
              //console.log("TOGGLE DOWN");
              targetIcon.classList.toggle("mouse-down")
	      if (targetIcon.classList.contains("mouse-down")) {
                  item_toggle_switch(e, true);

	      } else {
                  item_toggle_switch(e, false);

	      }
	      return;
	   }
           targetIcon.classList.add("mouse-down")
           item_mousedown(e);
       });
       icon.addEventListener("mouseup", function (e) {
           const targetIcon = this
           //const icon = targetIcon.parentElement
	   if (targetIcon.classList.contains("toggle")) {
              //console.log("TOGGLE UP");
	      return;
	   }
           targetIcon.classList.remove("mouse-down")
           item_mouseup(e);
       });
 
   });

});

/*
onMounted(() => {
});
*/
</script>

<template >
 <div class="item" ref="item"  :class="{ alignright : props.alignright  }" >
  <slot  ></slot>
 </div>
        <div class="tooltip" >
		<div class="tip_message">{{props.tooltip}}</div>
        </div>
</template>

<style >
/*
.icon {
 box-shadow: 2px 2px 0px 0px lightgray;
 box-shadow: -2px -2px 0px 0px lightgray;
}
*/

</style >

<style scoped>
.tooltip {
    position: relative;
    top: 50px;
    left: -20px;
    display: none;
}

.tooltip .tip_message {
	/*
    width: 100%;
    min-width: 80px;
    box-sizing: border-box;
    */
    position: absolute;
    margin-top: 4px;
    border-radius: 16px;
    /* background-color: #d8d8d8;*/
    background-color: #000000;
    color: #ffffff;
    font-size: 14px;
    line-height: 1.2;
    padding: 8px 14px;
}

.tip_active {
    display: block;
}

.alignright{
  margin-left: auto;
}

</style>
