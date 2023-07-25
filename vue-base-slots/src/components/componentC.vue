<template>
    <p>componentC</p>
    <p>{{ message }}</p>
</template>
<script>
export default {
    data() {
        return {
            msg: ""
        }
    },
    inject: ["message"]
}
</script>