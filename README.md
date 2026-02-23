# Ghostty 配置
个人 [Ghostty](https://ghostty.org) 终端配置（macOS）。

## 目录结构

```
~/.config/ghostty/
├── config          # 主配置
├── config-macos    # macOS 专属
├── config.local    # 单机定制（不入 Git）
└── .gitignore
```

## 配置亮点

| 项目 | 值 |
|------|------|
| 主题 | Under The Sea |
| 字体 | JetBrains Mono Nerd Font, 16pt |
| 清屏 | `Ctrl+L`（全局，含 SSH） |
| macOS Option | 左 Option = Alt |
| 标题栏 | 原生样式 |
| 热重载 | `Cmd+Shift+,` |

## 快速开始

### 第一步：安装字体
```bash
brew install --cask font-jetbrains-mono-nerd-font
```

### 第二步：克隆配置

```bash
git clone https://github.com/wenbochang888/ghostty-config.git ~/.config/ghostty
```

### 第三步：清理旧配置

macOS 有两个配置路径，需要清空旧的避免冲突：
```bash
echo '# Moved to ~/.config/ghostty' > ~/Library/Application\ Support/com.mitchellh.ghostty/config
```

### 第四步：重启 Ghostty

打开（或重启）Ghostty 即可生效。

## 单机定制（可选）

每台机器可以有自己的专属配置，不会被 Git 同步：

```bash
# 例：这台机器用更大的字号
echo 'font-size = 20' >> ~/.config/ghostty/config.local
```

## 日常同步

```bash
# 改了配置后推送
cd ~/.config/ghostty && git add -A && git commit -m 'update config' && git push

# 其他机器拉取
cd ~/.config/ghostty && git pull
```