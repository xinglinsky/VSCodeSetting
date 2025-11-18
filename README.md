# VSCodeSetting

## 描述

本仓库包含我的 VSCode/Cursor/Windsurf 编辑器配置和扩展插件设置，支持多设备同步。

## 配置文件结构

```
profiles/
├── cursor/          # Cursor 编辑器配置
│   └── data/
│       ├── extensions.yml        # 扩展插件列表
│       ├── settings.json         # 编辑器设置
│       ├── keybindings-windows.json  # Windows 快捷键配置
│       └── ui-state.yml         # UI 状态配置
└── windsurf/        # Windsurf 编辑器配置
    └── data/
        ├── extensions.yml
        ├── settings.json
        ├── keybindings-windows.json
        └── ui-state.yml
```

## 使用方法

### 1. 安装 Sync Settings 扩展

安装 [Sync Settings](https://marketplace.visualstudio.com/items?itemName=zokugun.sync-settings) 扩展用于同步配置。

### 2. 配置同步

在设置中配置同步资源：
- `extensions` - 扩展插件
- `keybindings` - 快捷键
- `settings` - 编辑器设置
- `snippets` - 代码片段
- `uiState` - UI 状态

### 3. 手动导入配置

如果需要手动导入配置，可以将对应配置文件复制到编辑器的用户配置目录：
- **Windows**: `%APPDATA%\Code\User\` (VSCode) 或 `%APPDATA%\Cursor\User\` (Cursor) 或 `%APPDATA%\Windsurf\User\` (Windsurf)

## 主要配置说明

### 编辑器设置

#### 通用设置
- **字体**: Cascadia Code（支持连字）
- **主题**: Catppuccin Mocha
- **图标主题**: catppuccin-mocha
- **自动保存**: 失去焦点时自动保存
- **文件嵌套**: 支持 TypeScript/JavaScript、package.json、SQLite 等文件的智能嵌套

#### Git 配置
- 同步时自动 rebase
- 自动获取远程更新
- 拉取时自动获取
- 获取时自动清理远程分支

#### 终端配置
- **默认终端**: PowerShell (Windows)
- **MSYS2 MinGW64**: 已配置 MSYS2 终端支持

### Vim 模式配置

#### 基本设置
- **Leader 键**: `<Space>`
- **EasyMotion**: 启用快速跳转
- **Sneak**: 启用快速搜索（替换 f/F）
- **CamelCase Motion**: 支持驼峰命名移动
- **智能相对行号**: 启用
- **系统剪贴板**: 启用

#### 自定义快捷键
- `<Space>w` - 保存文件
- `<Space>q` - 关闭当前编辑器
- `<Space>m` - 切换书签
- `<Space>b` - 显示书签列表
- `<Space>wt` - 切换终端
- `<Space>wo` - 切换输出面板
- `<Space>wp` - 显示问题面板
- `gm` - 跳转到符号
- `go` - 快速打开文件
- `gh` - 切换头文件/源文件（C/C++）
- `jj` - 插入模式下退出到普通模式

### 扩展插件列表

#### Cursor 配置插件

##### 编程语言支持
- **Python**: `ms-python.python`, `ms-python.vscode-pylance`, `ms-python.debugpy`, `anysphere.cursorpyright`
- **Java**: `redhat.java`, `vscjava.vscode-java-pack`, `vscjava.vscode-java-debug`, `vscjava.vscode-java-test`, `vscjava.vscode-maven`, `vscjava.vscode-gradle`
- **Go**: `golang.go`
- **Kotlin**: `fwcd.kotlin`
- **C/C++**: `llvm-vs-code-extensions.vscode-clangd`, `ms-vscode.cmake-tools`, `vadimcn.vscode-lldb`

##### 远程开发
- `anysphere.remote-containers` - 容器开发
- `anysphere.remote-ssh` - SSH 远程开发
- `anysphere.remote-wsl` - WSL 支持
- `ms-vscode-remote.vscode-remote-extensionpack` - 远程开发扩展包

##### Markdown 工具
- `DavidAnson.vscode-markdownlint` - Markdown 语法检查
- `shd101wyy.markdown-preview-enhanced` - 增强的 Markdown 预览
- `tchayen.markdown-links` - Markdown 链接工具
- `yzhang.markdown-all-in-one` - Markdown 全能工具

##### 图表和可视化
- `hediet.vscode-drawio` - Draw.io 图表编辑器
- `hediet.vscode-drawio-insiders-build` - Draw.io 内测版
- `jebbs.plantuml` - PlantUML 图表

##### 工具类
- `mechatroner.rainbow-csv` - CSV 文件高亮
- `qwtel.sqlite-viewer` - SQLite 数据库查看器
- `ms-vscode.hexeditor` - 十六进制编辑器
- `ms-vscode.powershell` - PowerShell 支持
- `VisualStudioExptTeam.vscodeintellicode` - IntelliCode AI 辅助
- `zokugun.cron-tasks` - 定时任务管理

##### 主题和图标
- `Catppuccin.catppuccin-vsc` - Catppuccin 主题
- `Catppuccin.catppuccin-vsc-icons` - Catppuccin 图标

#### Windsurf 配置插件

Windsurf 配置包含更精简的插件集合：
- **主题**: Catppuccin 主题和图标
- **图表**: Draw.io
- **数据库**: SQLite Viewer
- **编辑器**: Vim 模式
- **工具**: Cron Tasks

### 快捷键配置

#### Windsurf 特定快捷键
- 禁用了 Vim 的 `Ctrl+P` 和 `Ctrl+T` 快捷键，避免与编辑器默认快捷键冲突

## 注意事项

1. **路径配置**: 某些配置中包含绝对路径（如 clangd 路径），需要根据实际安装路径调整
2. **平台差异**: 快捷键配置针对 Windows 平台，其他平台可能需要调整
3. **扩展兼容性**: 部分扩展可能仅在特定编辑器版本可用
4. **同步设置**: 使用 Sync Settings 扩展时，确保配置了正确的同步资源

## 自定义配置

可以根据个人需求修改以下文件：
- `settings.json` - 编辑器设置
- `keybindings-windows.json` - 快捷键绑定
- `extensions.yml` - 扩展插件列表

修改后记得同步到其他设备或提交到仓库。
