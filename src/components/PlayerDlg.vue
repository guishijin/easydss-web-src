<template>
    <div id="bofangqiceshi">
        <VideoDlg ref="videoDlg"></VideoDlg>
        <Player @play="play"></Player>
    </div>
</template>

<script>
import Player from './Player.vue'
import VideoDlg from './VideoDlg.vue'

export default {
    name: "PlayerDlg",
    data() {
        return {
            msg:'PlayerDlg.msg'
        }
    },
    components: {
        Player, VideoDlg
    },
    methods: {
        btnClick(msg){
            alert(msg);
        },
        play(video){
            alert("Player.vue组件的父组件接收到 Player组件的消息!");
            this.$refs.videoDlg.play(video.videoUrl, video.videoTitle);
        }
    }
}
</script>

<style scoped>

</style>