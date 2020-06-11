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
