# Blog Hugo Configuration

本仓库用于存储 Hugo 博客的配置文件、主题和构建脚本。

---

## 📦 仓库说明

- **类型**: Hugo 构建仓库
- **用途**: 存储 Hugo 配置、内容和构建环境
- **部署目标**: jasonchio-cn.github.io

---

## 🚀 工作流程

```
ObsidianVault (内容仓库)
    ↓ 推文章
GitHub Actions
    ↓
拉取 blog-hugo-config (这里)
    ↓
合并 content/
    ↓
hugo build
    ↓
部署到 jasonchio-cn.github.io
```

---

## 📁 目录结构

```
blog-hugo-config/
├── hugo.yml           # Hugo 主配置文件
├── go.mod             # Go Modules 配置
├── go.sum             # 依赖锁定
├── content/           # 从 ObsidianVault 同步的内容
│   ├── post/         # 博客文章
│   ├── page/         # 页面
│   └── ...
├── assets/            # 资源文件
├── static/            # 静态文件
└── archetypes/        # 内容模板
```

---

## ⚙️ 配置说明

### hugo.yml
主配置文件，包含：
- 网站基础信息（title, baseURL）
- 多语言设置
- 主题参数
- 评论系统（Twikoo）
- 邮箱格式

### go.mod
使用 Go Modules 管理主题依赖：
```go
module github.com/jasonchio-cn/blog-hugo-config

require github.com/CaiJimmy/hugo-theme-stack/v3 v3.33.0
```

---

## 🔧 本地构建

```bash
# 克隆仓库
git clone https://github.com/jasonchio-cn/blog-hugo-config.git
cd blog-hugo-config

# 下载依赖（包括主题）
hugo mod get -u

# 本地预览
hugo server -D
```

---

## 📝 注意事项

- `content/` 目录在 Actions 构建时会从 ObsidianVault 同步覆盖
- 不要手动修改 `content/` 目录
- 如需修改文章，请在 ObsidianVault 操作
- 配置文件可以直接在本仓库修改

---

## 📦 部署状态

- **环境**: GitHub Actions
- **触发**: ObsidianVault 推送到 main 分支
- **目标**: jasonchio-cn.github.io/main 分支
- **访问地址**: https://blog.961110.xyz:10010

---

## 📄 License

MIT License
