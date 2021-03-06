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
* 用來專門設置 vue 的 出現、消失、切換等事件時的轉變動畫(ex: 切換頁面、內容出現消失)
* 若是單純的 class 跟 style 轉換，直接用 css3 的 transition 屬性設置即可
* 利用 transition 標籤設置 name 屬性，此 name 就會去找對應的 class，ex: fade-enter-active，fade 就是設置的 name
* v-enter-active: 可以在此設置 transition 屬性，告訴"進入動畫"的屬性、動畫時間、延遲時間，ex: transition: all 1s;
* v-leave-active: 跟上面的功能一樣，只是換成設置"離開動畫"
* v-enter: enter 時的初始狀態
* v-enter-to: enter 後的最後狀態
* v-leave: leave 時的初始狀態
* v-leave-to: leave 後的最終狀態
* 動畫順序可以參考官方教學中的圖: https://vuejs.org/v2/guide/transitions.html#Transition-Classes

<img src="https://vuejs.org/images/transition.png" height="300">

## Dynamic & Async Components
* 動態切換 component，利用 is 屬性可以隨時切換目前的 component，利用 keep-alive 標籤可以選擇是否保留狀態
* 動態載入 component，主要是想要需要時才載入，避免浪費不必要的載入時間 & 頻寬

動態切換 component
```
<component v-bind:is="currentTabComponent"></component>
```
動態載入 component
```
components: {
  'my-component': () => import('.vue')
}
```
