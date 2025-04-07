---
outline: deep
prev: "安卓版-如何安装插件"
next: "桌面版-如何安装插件"
---

<script setup>
import { ref, onMounted } from 'vue'

const appName = 'MusicAI 桌面版'
const latestVersion = ref(null);

const updateList = [
//   'https://gitee.com/fish-job/MusicFreeDesktop/raw/master/release/version.json',
//   'https://raw.githubusercontent.com/maotoumao/MusicFreeDesktop/master/release/version.json',
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

你可以从以下途径获取 {{ appName }} 的最新下载地址目前桌面版本已经停止更新：

## :yellow_heart: Github

更新时也会在 Github 同步更新（如果没有忘记的话...），你可以去 Github 仓库的 Releases 中下载最新版本：

[MusicAI 桌面版 Github Releases](https://github.com/fish-job/MusicFreeDesktop/releases)

## :blue_heart: 云盘

目前所有的版本会上传到云盘中，可在站点首页跳转到下载地址。

## :question: 我应该安装哪个文件

- Win10 及以上用户请安装 MusicAI-{version}-windows-setup.exe

- Win7 至 Win 8.1 用户请安装 MusicAI-{version}-windows-legacy-setup.exe

- Macos Intel 用户请安装 MusicAI-{version}-windows-macos-x86.dmg
