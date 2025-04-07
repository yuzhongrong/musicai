---
outline: deep

next: "安卓版-如何安装插件"
---

<script setup>
import { ref, onMounted } from 'vue'

const appName = 'MusicAI 安卓版'
const latestVersion = ref(null);

const updateList = [
    'https://gitee.com/fish-job/musicai-upgrade/blob/master/release/version.json'

];

onMounted(async () => {
    for (let i = 0; i < updateList.length; ++i) {
        try {
        const rawInfo = await fetch(updateList[i]).then(_ => _.json());
        latestVersion.value = rawInfo;
        console.log(latestVersion)
        break;
        } catch { }
    }
})

</script>

<style scoped>
.wechat-channel {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 160px;
}

.wechat-channel img {
    height: 160px;
}

</style>

# 如何安装应用 <Badge type="tip" v-if="latestVersion" :text="`最新版: ${latestVersion?.version}`" />

你可以从以下途径获取 {{ appName }} 的最新下载地址：

## :orange_heart: qq 频道

每次更新时都会在 qq 频道【MusicAI】推送:

<div class="qq-channel"><img src="/public/img/qq_channel.jpg" /></div>

## :yellow_heart: Github（二开后闭源开源的不值钱）

<!-- 更新时也会在 Github 同步更新（如果没有忘记的话...），你可以去 Github 仓库的 Releases 中下载最新版本： -->

<!-- [MusicAI 安卓版 Github Releases](https://github.com/fish-job/MusicFree/releases) -->

## :blue_heart: 云盘

目前所有的版本会上传到云盘中，可在站点首页跳转到下载地址。
