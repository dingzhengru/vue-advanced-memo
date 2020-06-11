# vue-advanced-memo
vue 的進階功能筆記

* [Slot](#slot)

## Slot
可以於 Component 內容中設置插入點，讓使用者可以在插入點放入自己的內容
* slot name 未設置的，即是 default
* slot 可以設置屬性，且使用者可以接收到這些屬性值
* 也可以插入 Compoent 中的 for loop 內容中(範例在: SlotForLoopData)

Component.vue
``` xml
<slot name="header">
  預設內容
</slot>
<main>
  <slot></slot> <!-- 等同於 <slot name="default"></slot> -->
</main>
```
App.vue
``` xml
<component>
  <template v-slot:default>
    插入內容
  </template>
</component>
```

## Transition
* 利用 vue 設置 css3 中的 transition 屬性(轉變動畫)
* 利用 transition 標籤設置 name 屬性，此 name 就會去找對應的 class，ex: fade-enter-active，fade 就是設置的 name
* v-enter-active: 可以在此設置 transition 屬性，告訴"進入動畫"的屬性、動畫時間、延遲時間，ex: transition: all 1s;
* v-leave-active: 跟上面的功能一樣，只是換成設置"離開動畫"
* v-enter:
* v-enter-to
* v-leave
* v-leave-to
* 動畫順序可以參考官方教學中的圖: https://vuejs.org/v2/guide/transitions.html#Transition-Classes

<img src="https://vuejs.org/images/transition.png" height="200">
