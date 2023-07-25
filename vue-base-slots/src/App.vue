<template>
<SlotsComponent>
    <!-- <template #header>
      <h3>golang</h3>
    </template>
    <template v-slot:main>
      <h3>c++</h3>
    </template> -->
    <template #header="slotProps">
      <p>{{ msg }}--{{ slotProps.msg }}</p>
    </template>
    <template #main="slotProps">
      <p>{{ slotProps.job }}</p>
    </template>
</SlotsComponent>
<LifeDemo/>
<KeepAlive>
  <component :is="tabComponent"></component>
</KeepAlive>
<button @click="changeHandle">切换组件</button>
</template>
<script>
import { defineAsyncComponent } from "vue"
import SlotsComponent from "./components/SlotsComponent.vue"
import LifeDemo from "./components/LifeDemo.vue"
import componentA from "./components/componentA.vue"
// import componentB from "./components/componentB.vue"

// 异步加载
const componentB = defineAsyncComponent(() => 
  import("./components/componentB.vue")
)
export default {
  data() {
    return {
      msg: "传递主数据",
      tabComponent: "componentA"
    }
  },
  components: {
    SlotsComponent,
    LifeDemo,
    componentA,
    componentB
    },
  methods: {
    changeHandle() {
      this.tabComponent = this.tabComponent == "componentA" ? "componentB" : "componentA"
    }
  },
  provide: {
    message: "A的财产"
  },
}
</script>
<style>
</style>
