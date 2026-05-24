# exam

## 启动 FlClash

```bash
cd ~/Downloads
```

```bash
./FIClash-0.8.92-linux-amd64.AppImage --appimage-extract
```

```bash
cd squashfs-root
```

```bash
./AppRun
```

然后：

1. 左侧点 配置
2. 添加配置
3. 选 URL
4. 开系统代理

---
https://naiun.adfgawidhioawjd.site/api/v1/client/subscribe?token=12673c013aee9d551eb1194da890cb94

https://naiun.adfgawidhioawjd.site/api/v1/client/subscribe?token=12673c013aee9d551eb1194da890cb94
然后打开网页 AI

https://b3.342242.icu/api/v1/client/subscribe?token=6043402282b557cc3610036229014d65

或者可以https://github.com/chen08209/FlClash/releases直接下载，这机器可以直接访问GitHub，还挺快的

sk-6d6db6b0e2aa44cb91a94af559afc3a2

APPIMAGE_EXTRACT_AND_RUN=1 ./FIClash-0.8.92-linux-amd64.AppImage

https://b3.342242.icu/api/v1/client/subscribe?token=6043402282b557cc3610036229014d65
## 明天 Linux 配置 Claude Code 完整流程

### 第一步：开启代理
打开 FlClash，确认 System proxy 已开启，代理端口 **7890**。

验证代理是否通：
```bash
curl -I --proxy http://127.0.0.1:7890 https://api.anthropic.com
```
返回非 403 就说明通了。

---

### 第二步：安装 Node.js（无需 sudo）
```bash
# 安装 nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# 重新加载环境
source ~/.bashrc

# 安装 Node.js
nvm install 20
nvm use 20

# 验证
node -v
npm -v
```

---

### 第三步：安装 Claude Code
```bash
export HTTPS_PROXY=http://127.0.0.1:7890
export HTTP_PROXY=http://127.0.0.1:7890

npm install -g @anthropic-ai/claude-code

# 验证
claude --version
```

---

### 第四步：设置代理永久生效
```bash
echo 'export HTTPS_PROXY=http://127.0.0.1:7890' >> ~/.bashrc
echo 'export HTTP_PROXY=http://127.0.0.1:7890' >> ~/.bashrc
source ~/.bashrc
```

---

### 第五步：登录 Claude Code
```bash
claude
```
浏览器打开后选 **Claude.ai Subscription**，登录你的 Claude Pro 账号。

---

### 第六步：VS Code 插件配置
扩展商店搜 **Claude Code**（Anthropic 官方），安装。

按 `Ctrl+Shift+P` → 输入 `Open User Settings JSON` → 添加：

```json
{
    "http.proxy": "http://127.0.0.1:7890",
    "http.proxySupport": "override",
    "http.proxyStrictSSL": false,
    "claudeCode.environmentVariables": [
        {
            "name": "HTTP_PROXY",
            "value": "http://127.0.0.1:7890"
        },
        {
            "name": "HTTPS_PROXY",
            "value": "http://127.0.0.1:7890"
        }
    ]
}
```

**完全关闭 VS Code 再重新打开**，然后登录插件。

---

### 注意事项
- 全程不需要 sudo
- 每次新开终端如果代理失效，手动运行 `source ~/.bashrc`
- 登录选 **Claude.ai Subscription**

---
