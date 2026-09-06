# MCSM管理器（HarmonyOS）

MCSManager 面板的第三方鸿蒙（HarmonyOS）手机管理端。在手机上连接你自建的 MCSManager 面板（v10+），随时随地查看服务器监控、管理游戏实例。

> 本项目与 MCSManager 官方无关。MCSManager 基于 Apache-2.0 协议开源。

## 项目介绍

这是一个纯鸿蒙原生（ArkTS）应用，服务于所有自建 MCSManager 面板的服主：面板通常跑在家里 NAS、VPS 或内网机器上，网页管理在手机上体验不佳，本应用为手机场景做了完整的触屏适配。

工作方式：用户填入面板地址与 APIKEY（面板「用户设置」中获取），应用直接调用 MCSManager 的 HTTP API 完成全部管理操作，本应用自身不经过任何第三方服务器，所有数据只在手机与你的面板之间传输。



## 侧载安装指引（不经应用市场安装）

本应用未上架时，可用 GitHub 开源侧载工具 [**auto-installer**](https://github.com/likuai2010/auto-installer)（封装官方 hdc 调试通道，俗称"小白鸿蒙自助餐"）直接安装，全程不需要应用市场。

### 准备工作

1. **手机端**（HarmonyOS 6.x）：
   - 设置 → 关于本机 → 连续点击「软件版本」7 次 → 提示已进入开发者模式
   - 设置 → 系统与更新 → 开发者选项 → 打开「USB 调试」
   - 用数据线连接电脑，手机弹出的"允许 USB 调试"选择允许
2. **电脑端**：
   - 到 [auto-installer 的 GitHub Releases](https://github.com/likuai2010/auto-installer/releases) 下载最新版并解压
3. **安装包**：
   - 本项目 Releases 提供两种包：`.hap`（单包）与 `.app`（上架聚合包），侧载选 `.hap` 即可；若工具版本支持直接安装 `.app` 亦可

### 安装步骤

1. 运行 auto-installer，它会自动检测已连接的鸿蒙设备
2. 选择「安装应用」，指向下载的 `.hap` 文件（如 `entry-default-signed.hap`）
3. 等待提示安装成功，桌面出现「MCSM管理器」

### 常见问题

- **检测不到设备**：确认 USB 调试已开、数据线支持数据传输、手机上已授权这台电脑
- **签名有效期提示**：用调试证书签名的包有效期为 14 天（完成开发者实名认证后 180 天），到期需重装；本项目提供的发布签名包无此限制
- **想省事**：如果你只是自己用，也可以直接用 DevEco Studio 打开工程连真机 Run（自动签名），效果等同
- **上传自己的包**：把 `D:\mcsm-assets\releases\<版本>\` 里的 `*-signed.app` / `*-unsigned.hap` 发布到你的 GitHub Releases 即可分发（未签名 hap 需自行签名后再分发）

## 相关文档

- 反馈邮箱：bamboos233@petalmail.com
