<div align="center">
  <p><a href="./ReadMe.md">English</a> | <strong>简体中文（zh-CN）</strong></p>

  <img src="./images/logo-mini-2.webp" alt="ImgCompress 标志" height="80px" />
  <h1>ImgCompress</h1>
  <p><strong>全格式图像处理，零云端依赖。</strong></p>
  <p>转换 70 多种格式、逐文件裁剪、批量压缩，并使用本地 AI 移除背景。界面支持 12 种语言。<br/>所有处理都在你的容器中完成，文件绝不会离开你的服务器。</p>

  <p>
    <a href="https://imgcompress.karimzouine.com/">
      <img src="https://img.shields.io/badge/功能与特性-%E2%86%92-0f172a?style=for-the-badge&logo=gitbook&logoColor=white" alt="功能与特性" />
    </a>
    <a href="https://imgcompress.karimzouine.com/docs/installation">
      <img src="https://img.shields.io/badge/安装指南-%E2%86%92-1e40af?style=for-the-badge&logo=gnubash&logoColor=white" alt="安装指南" />
    </a>
  </p>

  <p>
    <a href="https://hub.docker.com/r/karimz1/imgcompress"><img src="https://img.shields.io/docker/pulls/karimz1/imgcompress?style=flat-square&color=0db7ed&label=Docker%20Pulls&logo=docker&logoColor=white" alt="Docker 下载量" /></a>
    <a href="https://github.com/karimz1/imgcompress"><img src="https://img.shields.io/github/stars/karimz1/imgcompress?style=flat-square&color=f4d03f&label=Stars&logo=github&logoColor=black" alt="GitHub Star 数量" /></a>
    <a href="./TRANSLATIONS.md"><img src="https://img.shields.io/badge/多语言-12%20种语言-16a34a?style=flat-square&logo=googletranslate&logoColor=white" alt="支持 12 种语言" /></a>
  </p>

  <p>
    <a href="https://imgcompress.karimzouine.com/">网站</a> ·
    <a href="https://imgcompress.karimzouine.com/docs">文档</a> ·
    <a href="https://imgcompress.karimzouine.com/docs/installation">安装指南</a> ·
    <a href="https://hub.docker.com/r/karimz1/imgcompress">Docker Hub</a> ·
    <a href="https://github.com/karimz1/imgcompress/issues">问题反馈</a>
  </p>

  <br />

  <img src="./images/web-ui/web-ui-upload-configure.webp" alt="ImgCompress 网页界面：上传并配置图像" width="100%" />
</div>

---

## ImgCompress 是什么？

ImgCompress 是一个完全运行在单个 Docker 容器中的**自托管图像处理服务**。它可以在你自己的硬件上完成图像压缩、格式转换和 AI 背景移除，无需调用云端 API、向第三方上传文件，也不会跟踪用户。

它适合普通用户、家庭实验室爱好者，以及所有重视隐私和数据所有权的人。

---

## 功能特性

| 功能 | 说明 |
|---|---|
| **70 多种图像格式** | 支持 HEIC、HEIF、PSD、AVIF、EPS、PDF、WebP、TIFF、BMP、GIF 等 70 多种格式 |
| **本地 AI 背景移除** | 内置模型在 CPU 上运行，无需 API 密钥、订阅或上传文件 |
| **批量压缩** | 利用多核并行处理整个照片库 |
| **格式转换** | 支持 HEIC 转 WebP、PSD 转 JPG、批量图像转多页 PDF 等 |
| **逐文件裁剪** | 转换前可分别裁剪每个文件，支持自由比例、1:1、16:9、4:3 及自定义像素尺寸 |
| **网页界面与 CLI** | 网页控制台适合日常使用，CLI 适合自动化脚本 |
| **单一容器** | 所有编解码器和依赖库均已内置，主机无需安装额外依赖 |
| **支持离线环境** | 拉取镜像后可完全离线运行，不再需要互联网连接 |

---

## 本地、私密的 AI 背景移除

无需再把个人照片或客户照片上传到云端抠图服务。ImgCompress 内置 AI 模型，在**你自己的硬件**上移除背景。无需 API 调用或订阅，文件始终保留在你的服务器中。

| 原图 | 移除背景后 |
|:---:|:---:|
| <img src="images/image-remover-examples/landscape-with-sunset-yixing-original.avif" width="380" alt="日落风景原图"/> | <img src="images/image-remover-examples/landscape-with-sunset-yixing-ai-transparency.avif" width="380" alt="通过本地 AI 移除背景后的风景图"/> |

---

## 逐文件裁剪（自 v0.7.0 起）

每个上传的文件都可以在转换前单独裁剪。你可以选择自由比例、1:1、16:9、4:3 等预设，也可以输入精确的像素宽度和高度。裁剪设置会按文件保存，因此同一批次可以同时处理正方形缩略图和 16:9 封面，无需重新上传。

<img src="images/web-ui/web-ui-crop-feature.webp" alt="ImgCompress 裁剪界面，包含宽高比预设、缩放滑块、像素尺寸和键盘快捷键" width="100%" />

### 使用方法

1. 像往常一样将图像拖入上传区域。
2. 点击任意文件行中的裁剪图标，打开编辑器。
3. 选择宽高比预设（1:1、4:3、16:9 等），或手动设置宽度和高度。
4. 缩放并调整裁剪区域，精确完成构图。
5. 点击**保存**保留裁剪，点击**放弃**退出，或点击**移除**清除之前保存的裁剪。
6. 按正常流程开始转换。系统会先裁剪，再应用格式、质量、缩放和背景移除设置。

> [!NOTE]
> **服务器端渲染格式：** PSD、EPS 等格式会先在服务器端渲染为适合裁剪的位图，因此仍可在浏览器中裁剪。

完整教程和演示视频：**[图像裁剪编辑器文档](https://imgcompress.karimzouine.com/docs/web-ui#image-crop-editor)**。

---

## 快速开始

拉取镜像，打开 `localhost:3001`，即可开始转换，整个过程大约需要 60 秒。

```bash
docker run -d \
  --name imgcompress \
  -p 3001:5000 \
  karimz1/imgcompress:latest
```

更喜欢 Docker Compose？[`docker/compose/`](docker/compose/) 中提供了现成配置：

- **[advanced.docker-compose.yaml](docker/compose/advanced.docker-compose.yaml)**：适用于家庭或局域网环境，可从网络中的任意设备访问，并包含日志轮换、健康检查和 `no-new-privileges` 等容器最佳实践。
- **[proxied.docker-compose.yaml](docker/compose/proxied.docker-compose.yaml)**：适用于通过域名和 HTTPS 部署，使用 Traefik 反向代理、TLS、安全响应头及可选的 Let's Encrypt。

两种方案的分步说明请参阅 **[Compose 指南](docker/compose/README.md)**。

环境变量及隐藏吉祥物的部署方式，请参阅**[完整安装指南](https://imgcompress.karimzouine.com/docs/installation)**。

---

## 为什么开发 ImgCompress？

我厌倦了反复安装软件的怪圈。每当需要完成一个简单任务，就要再安装一个应用：

- **PSD 文件**：仅仅为了转换成普通图像，就需要专用软件。
- **HEIC 文件**：转换为常用图片格式又需要另一个工具。
- **图像转 PDF**：为了在工作邮件中分享截图，还需要额外的应用将其转为便于打印的 PDF。
- **AI 背景移除**：这个功能似乎又需要一个新应用。

我想：“为什么不能用一个工具完成所有这些任务？”而且，把私人照片上传到不熟悉的在线转换网站始终让人不放心。

### 一个工具箱解决所有问题

因此，我开发了这个可以处理 **70 多种格式**的统一工具箱。无论是将 PSD 或 HEIC 转换为常用图片格式、把工作截图制作为 PDF，还是压缩巨大的 4K 照片，它都能自动完成。

如今，社区已经拉取该镜像数万次，这说明这个需求真实存在。

### 为什么选择 Docker？

Docker 可以保持你的计算机整洁。你无需在系统中安装 70 个复杂的依赖库，因为我已将所有内容打包进一个可在任何地方运行的**开箱即用容器**：**imgcompress**。

---

## 隐私优先设计

| | |
|---|---|
| **无云端处理** | 转换、压缩和 AI 推理全部在本地运行，图像不会离开你的设备。 |
| **无遥测** | 不收集分析数据，不发送崩溃报告，功能开关也不会连接外部服务；启动后不会产生不必要的网络通信。 |
| **拉取后离线运行** | 镜像拉取完成后不再需要互联网连接，没有许可证检查或过期限制。 |
| **开源** | 采用 GPL-3.0 许可证，可审查源代码、派生项目并永久自托管。 |

---

## 安全加固的 Docker 镜像

ImgCompress 使用经过安全加固的精简镜像，默认遵循常见的容器安全标准。

| | |
|---|---|
| **最小攻击面** | 不包含 shell（`bash`、`sh`）、网络工具（`curl`、`wget` 等）或包管理器，大幅减少攻击面。 |
| **精简组件** | 严格裁剪系统依赖，保持最小化运行环境。 |
| **非 root 用户** | 默认以非 root 用户 `nonroot` 运行。 |
| **DHI 基础镜像** | 构建和运行阶段使用 Docker 官方的 [Docker Hardened Images](https://www.docker.com/products/hardened-images/)（DHI）。 |
| **SBOM 与来源证明** | Docker 镜像包含完整的软件物料清单（SBOM）和构建来源证明。 |

---

## 多语言支持

ImgCompress 支持多种前端语言，也欢迎社区改进翻译。请参阅**[翻译贡献指南](TRANSLATIONS.md)**，添加新语言、改进现有翻译或获得贡献者署名。

支持的语言：英语、西班牙语、墨西哥西班牙语、简体中文、印地语、阿拉伯语、法语、巴西葡萄牙语、俄语、日语、德语和匈牙利语。

---

## 收录平台

ImgCompress 已获得自托管社区认可，并被多个常用平台和精选列表收录：

- **[Awesome Self-Hosted](https://github.com/awesome-selfhosted/awesome-selfhosted#readme)** [![Stars](https://img.shields.io/github/stars/awesome-selfhosted/awesome-selfhosted?style=flat-square&label=&color=f4d03f&logo=github&logoColor=black)](https://github.com/awesome-selfhosted/awesome-selfhosted)：由社区维护的自托管软件精选列表。[查看 ImgCompress 条目](https://awesome-selfhosted.net/index.html#imgcompress)。
- **[Coolify](https://github.com/coollabsio/coolify)** [![Stars](https://img.shields.io/github/stars/coollabsio/coolify?style=flat-square&label=&color=f4d03f&logo=github&logoColor=black)](https://github.com/coollabsio/coolify)：开源、自托管的部署平台。ImgCompress 是其**官方服务**，可直接从 Coolify 控制台添加。[查看 ImgCompress 条目](https://coolify.io/docs/services/imgcompress?utm_source=github.com)。

> 如果你知道其他收录 ImgCompress 的平台，或希望将它添加到某个平台，请[联系我们](https://www.karimzouine.com/#contact)。感谢开源社区帮助更多人发现 ImgCompress。

---

## 文档

- [安装与配置](https://imgcompress.karimzouine.com/docs/installation)：Docker 设置、环境变量和反向代理示例
- [开发者指南](https://imgcompress.karimzouine.com/docs/developers)：VS Code Dev Container、架构概览和本地环境设置
- [imgcompress-chan（机器人）](https://imgcompress.karimzouine.com/docs/imgcompress-chan)：用于修复 Dependabot pnpm 锁文件并自动合并依赖更新 PR 的辅助机器人
- [使用 Playwright 进行 E2E 测试](https://imgcompress.karimzouine.com/docs/e2e)：了解如何验证 70 多种格式的离线稳定性
- [致谢与依赖库](https://imgcompress.karimzouine.com/docs/credits)：为 ImgCompress 提供支持的开源项目
- [荣誉榜](https://imgcompress.karimzouine.com/docs/hall-of-fame)：赞助者和贡献者

---

## 参与贡献

欢迎提交错误报告、格式支持请求或 Pull Request（PR）。

> [!TIP]
> **第一次参与贡献？** 项目提供 VS Code Dev Container，已经配置好 70 多个图像处理库和 AI 环境，不到一分钟即可搭建开发环境。请阅读[开发者指南](https://imgcompress.karimzouine.com/docs/developers)。

- 提交 PR 前请阅读**[贡献指南](contributing.md)**
- 可从 [`good-first-issue`](https://github.com/karimz1/imgcompress/labels/good-first-issue) 标签中选择入门任务
- 每项更改都会通过覆盖所有支持格式的 Playwright E2E 测试验证

> [!NOTE]
> **认识一下 [imgcompress-chan](https://imgcompress.karimzouine.com/docs/imgcompress-chan)**：这是项目的自定义辅助机器人。CI 通过后，它会自动合并 Dependabot PR；如果前端依赖更新导致 `pnpm-lock.yaml` 损坏，它也可以协助修复。

---

## 许可证与作者

**作者**：[Karim Zouine](https://www.karimzouine.com)<br/>
**许可证**：[GPL-3.0](LICENSE)<br/>
**Docker 镜像**：[hub.docker.com/r/karimz1/imgcompress](https://hub.docker.com/r/karimz1/imgcompress)

如果 ImgCompress 为你节省了时间，欢迎在 GitHub 上点一个 Star，让更多人发现它。
