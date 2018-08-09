<template>
    <div class="container-fluid no-padding">
        <button class="btn btn-success" @click.prevent="btnClick">{{btnText}}</button>
    </div>
</template>

<script>
export default {
    props: {
        btnText: {
            type: String,
            default: "点我向父组件发送消息（即通过$emit触发父组件的btnClick事件）"
        }
    },
    methods: {
        btnClick() {
            this.$emit("btnClick", "hello");
        }
    }
}
</script>

<style lang="less" scoped>

</style>

