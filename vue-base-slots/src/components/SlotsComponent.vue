<template>
    <p>slots的基础知识</p>
    <!-- <slot name="header"></slot>
    <hr>
    <slot name="main"></slot> -->
    <slot name="header" :msg="msg"></slot>
    <hr>
    <slot name="main" :job="job"></slot>
</template>
<script>
export default {
    data() {
        return {
            msg: "传递次数据",
            job: "developer"
        }
    }
}
</script>