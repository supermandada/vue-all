<template>
    <h3>生命周期</h3>
    <p>{{ msg }}</p>
    <button @click="updateHandle">修改</button>
    <p ref="name">golang</p>
    <ul>
        <li v-for="(item,index) of banner" :key="index">
            <h3>{{ item.title }}</h3>
            <p>{{ item.content }}</p>
        </li>
    </ul>
</template>

<script>
export default {
    data() {
        return {
            msg: "更新前",
            banner: []
        }
    },
    methods: {
        updateHandle() {
            this.msg = "更新后"
        }
    },
    beforeCreate() {
        // console.log("创建之前");
        console.log(this.$refs.name);
    },
    created() {
        // console.log("创建之后");
        console.log(this.$refs.name);
    },
    beforeMount() {
        // console.log("渲染之前");
        console.log(this.$refs.name);
    },
    mounted() {
        // console.log("渲染之后");
        console.log(this.$refs.name);
        this.banner = [
            {
                title: "golang",
                content: "content of golang"
            },
            {
                title: "python",
                content: "content of python"
            }
        ]
    },
    beforeUpdate() {
        // console.log("更新之前");
        console.log(this.$refs.name);
    },
    updated() {
        // console.log("更新之后");
        console.log(this.$refs.name);
    },
    beforeUnmount() {
        // console.log("卸载之前");
        console.log(this.$refs.name);
    },
    unmounted() {
        // console.log("卸载之后");
        console.log(this.$refs.name);
    }
}
</script>