<script setup lang="ts">

import { ref , defineProps, defineEmits, onMounted, useTemplateRef} from 'vue';

const props = defineProps(['tooltip']);


const emit = defineEmits(['toolbarItemClick']);
const item  = useTemplateRef('item')

function item_mousedown(e) {
     console.log("down", e.target);
      emit('toolbarItemClick', "aiueo")
}
function item_mouseup(e) {
     console.log("up");
}

onMounted(() => {
     const icons = item.value.querySelectorAll(".icon")
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
       icon.addEventListener("mousedown", item_mousedown);
       icon.addEventListener("mouseup", item_mouseup);
 
   });

});

/*
onMounted(() => {
});
*/
</script>

<template >
 <div class="item" ref="item">
  <slot  ></slot>
 </div>
        <div class="tooltip" >
		<div class="tip_message">{{props.tooltip}}</div>
        </div>
</template>

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
</style>
