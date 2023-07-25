<template>
    <p>componentB</p>
</template>
<script>
export default {
    data() {
        return {
            msg: ""
        }
    },
    beforeUnmount() {
        console.log("组件B卸载之前");
        // console.log(this.$refs.name);
    },
    unmounted() {
        console.log("组件B卸载之后");
        // console.log(this.$refs.name);
    }
}
</script>