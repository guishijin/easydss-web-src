<template>
    <div class="container-fluid no-padding">
        <br>
        <div class="col-sm-8 col-sm-offset-2">
            <form role="form" class="form-horizontal" id="url-form">
                <div class="form-group">
                    <div class="input-group" id="input-url-group">
                        <input type="text" class="form-control" id="input-url" name="url" placeholder="输入播放地址" v-model.trim="url" @keydown.enter.prevent="play">
                        <span class="input-group-btn">
                            <a class="btn btn-primary" role="button" @click.prevent="play">
                                <i class="fa fa-play"></i> 播放</a>
                        </span>
                    </div>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
import Vue from 'vue'
import { Message } from 'element-ui'

Vue.prototype.$message = Message;

export default {
    name: 'Player',
    data() {
        return {
            url: "http://172.16.10.10:8888/hls/v1/token1/hls.m3u8"
        }
    },
    methods: {
        play() {
            if (!this.url) {
                this.$message({
                    type: 'error',
                    message: "播放地址不能为空"
                });
                return;
            }
            alert("播放地址正常!!!!!!! url = "+this.url);
            this.$emit("play", { videoUrl: this.url, videoTitle: this.url});
        }
    }
}
</script>

<style scoped>

</style>