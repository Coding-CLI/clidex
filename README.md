# Clidex CLI

原生 Claude 与 Codex 命令行体验。macOS / Linux / Windows。

## 安装

```bash
curl -fsSL https://clidex.dev/install.sh | sh
```

Windows 到 [Releases](https://github.com/Coding-CLI/clidex/releases/latest)
下载 `clidex-windows-amd64.exe`。

手动安装把 `<版本>` 换成 Releases 页上的 tag：

```bash
curl -fsSLO https://github.com/Coding-CLI/clidex/releases/download/<版本>/clidex-darwin-arm64
curl -fsSLO https://github.com/Coding-CLI/clidex/releases/download/<版本>/checksums.txt
shasum -a 256 -c checksums.txt --ignore-missing
chmod +x clidex-darwin-arm64 && sudo mv clidex-darwin-arm64 /usr/local/bin/clidex
```

## 开始

```bash
clidex init <platform_url> <token>   # token 在网页控制台的「我的 Token」页面复制
cd /path/to/project
clidex
```

`init` 的地址要用 Token 页面给出的那个（机器接口地址），不是网页控制台地址。
不加参数默认使用 Claude，`--codex` 切换到 Codex。

| 命令                        | 作用                             |
|-----------------------------|----------------------------------|
| `clidex`                    | 开启交互式终端                   |
| `clidex init <url> <token>` | 一次性配对账号                   |
| `clidex status`             | 查看计费方式、额度使用情况与余额 |
| `clidex tray`               | 系统托盘常驻显示额度             |
| `clidex version`            | 版本信息                         |

## 产物

每个 release 包含五个二进制与一份 `checksums.txt`：

| 文件                       | 平台                |
|----------------------------|---------------------|
| `clidex-darwin-arm64`      | macOS Apple Silicon |
| `clidex-darwin-amd64`      | macOS Intel         |
| `clidex-linux-amd64`       | Linux x86_64        |
| `clidex-linux-arm64`       | Linux aarch64       |
| `clidex-windows-amd64.exe` | Windows x64         |

静态单文件，无运行时依赖。安装脚本会校验 sha256，对不上即中止。

## 反馈

问题与建议请提 [Issues](https://github.com/Coding-CLI/clidex/issues)。
