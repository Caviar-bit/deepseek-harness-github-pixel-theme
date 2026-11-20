# GitHub Pixel · 像素栖地
[在线功能介绍与交互演示](https://caviar-bit.github.io/deepseek-harness-github-pixel-theme/) · [完整主题 ZIP](GitHub像素主题.zip) · [源码 ZIP](dsh-github-pixel-theme-source-1.2.3.zip)

为 DeepSeek Harness 制作的像素互动主题。以 GitHub 首页的彩色像素网格为灵感，结合独立底色、Clawd 桌面宠物与 Claude 风格星芒。

## 功能

- 像素网格、鼠标彩色拖尾与可选点击扩散；支持大小、消退时间、强度、显示范围和减少动态效果。
- 主界面、侧边栏、输入框与卡片分别改色，浅色与深色颜色分别保存。
- GitHub、DeepSeek、森林、暮色与自定义配色，支持跟随系统或宿主外观。
- 输入框上沿的 Clawd 宠物，随会话状态切换姿态；可设置显示范围、大小与开关。
- 输出中状态选择 Claude 星芒时只显示星芒，选择 Harness 原生时只显示原生鲸鱼尾巴；保留状态文字和计时。
- 已完成回复末尾的星芒签名，支持仅最新回复、每条已完成回复或关闭。
- 字体、字号、对话宽度、卡片圆角，以及 JSON 配置导入与导出。

## 安装

1. 下载并解压 `GitHub像素主题.zip`，或直接下载当前版本的 `.tgz` 安装包。
2. 关闭其他完整主题，避免样式叠加。
3. 在安装包所在目录运行：

```powershell
dsh plugin --profile desktop add "./dsh-github-pixel-theme-1.2.3.tgz"
```

4. 重启 Harness。点击新会话右下角四色按钮，在“像素主题设置”中调整功能。

Windows 用户已配置 `dsh` 命令后，也可以运行 ZIP 中的“安装到桌面版.cmd”。找不到命令时，请使用本机 Harness 的 CLI 终端或将其 CLI 加入 PATH。

网页版使用同一安装包，将 `desktop` 换成对应 profile，例如 `web`，然后重启服务并刷新页面。本主题未发布到 npm，请使用本地 `.tgz` 文件安装。

## 设置入口

| 分组 | 功能 |
| --- | --- |
| 外观 | 主题开关、亮暗模式、配色和强调色 |
| 底色 | 主界面、侧边栏、输入框与卡片的独立底色 |
| 像素互动 | 拖尾、点击扩散、角落四色装饰、网格和性能参数 |
| 宠物星芒 | Clawd、输出图标、回复签名与星芒颜色 |
| 布局字体 | 字体、字号、对话宽度和卡片圆角 |
| 配置 | JSON 导入、导出和恢复默认 |

首页原生像素鲸鱼背景已隐藏。左右上角的四色装饰可在“像素互动 → 角落彩色方块”中关闭。

## v1.2.3

修复真实 Harness 侧边栏调色不生效，适配原生 sidebar-fill 颜色变量与 AppFrame 容器。完整十六进制色号输入后立即应用，无需移开焦点；浅色与深色分别保存，刷新后保留。更新后请重启 Harness。

### v1.2.2

修复输出中鲸鱼尾巴与星芒同时显示的问题。两种输出图标按选项切换；状态文字、计时和无障碍播报保留。更新后请重启 Harness，原有主题配置可继续使用。

## 源码与验证

完整可编辑源码包含在源码 ZIP 和完整主题 ZIP 内。解压源码后运行：

```text
node build.mjs
node --test tests/activity.test.mjs tests/preferences.test.mjs tests/host-theme.test.mjs
```

构建无第三方依赖，需要 Node.js 22.18 或更新版本。发布前通过 12 项自动测试，并在本地预览验证星芒替换、原生恢复、重新渲染、减少动效和卸载清理。真实模型会话与不同实体手机未作完整实测。

面向 DeepSeek Harness 0.2.x，最低声明版本为 `0.2.1-rc.3`；测试使用 Desktop `0.2.1-rc.5`。宿主更新界面结构或插件接口时可能需要适配。

## 素材与许可

代码采用 MIT 许可，见 `LICENSE`。设置结构参考 [Nwflower/dsh-claude-style](https://github.com/Nwflower/dsh-claude-style)，像素互动灵感来自 [GitHub 首页](https://github.com/)。

Clawd 角色、图集和星芒等品牌素材不适用代码的 MIT 许可，权利归相应权利人；原始说明保留在 `ARTWORK-NOTICE.txt` 和源码素材目录中。本项目为非官方个人主题，与 GitHub、DeepSeek 或 Anthropic 无隶属关系。
