<template>
    <p>componentA</p>
    <p ref="name">{{ msg }}</p>
    <button @click="uploadHandle">更新数据</button>
</template>
<script>
import componentC from './componentC.vue';
export default {
    data() {
        return {
            msg: "老数据"
        }
    },
    beforeUnmount() {
        // console.log("卸载之前");
        console.log(this.$refs.name);
    },
    unmounted() {
        // console.log("卸载之后");
        console.log(this.$refs.name);
    },
    methods: {
        uploadHandle() {
            this.msg = "新数据"
        }
    },
    components: {
        componentC
    }
}
</script>