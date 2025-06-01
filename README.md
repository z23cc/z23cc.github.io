# Notion + Hexo + GitHub Actions + GitHub Pages 博客解决方案

# 博客工具

- 写作平台：Notion
- 博客平台：[Hexo](https://hexo.io/)
- 博客主题：[Butterfly@4.10.0](https://github.com/jerryc127/hexo-theme-butterfly)
- 博客文档同步：[Elog](https://github.com/LetTTGACO/elog)
- 部署平台：GitHub Pages
- CI/CD：GitHub Actions

# 博客搭建指南


## 1. Fork模板仓库


[点击 Fork](https://github.com/elog-x/notion-hexo/fork) 该模板仓库到个人 Github 账号仓库下并 clone 到本地


## 2. 安装依赖


在项目根目录下运行命令安装依赖


```shell
npm install
```


## 3. 新建 Elog 本地调试文件


在项目根目录中复制`.elog.example.env`文件并改名为`.elog.env`，此文件将用于本地同步Notion 文档


## 4. 配置 Notion 关键信息


按照[文档提示](https://elog.1874.cool/notion/gvnxobqogetukays#notion)配置 Notion 并获取 `token` 和 `databaseId`，在本地`.elog.env`中写入


```text
NOTION_TOKEN=获取的token
NOTION_DATABASE_ID=获取的databaseId
```


## 5.本地调试


在项目根目录运行同步命令


```shell
npm run sync:local
```


## 6.启动 Hexo


在项目根目录运行hexo启动命令，会自动打开本地博客


```shell
npm run server
```


## 7. 配置 Hexo 博客


根据 [Hexo](https://hexo.io/) 文档和 [Butterfly](https://github.com/jerryc127/hexo-theme-butterfly) 主题配置文档，配置你的博客直到你满意为主，你也可以换别的主题，这里不做演示


## 8. 提交代码到 github


本地访问没问题直接提交所有文件到 Github 仓库即可


## 9. 配置 GitHub Pages

本项目已配置为使用 GitHub Pages 进行部署，无需 Vercel。

### 9.1 启用 GitHub Pages
1. 进入 GitHub 仓库的 **Settings** → **Pages**
2. 在 **Source** 中选择 **GitHub Actions**
3. 详细设置请参考：[GitHub Pages 设置指南](./GITHUB_PAGES_SETUP.md)

### 9.2 访问地址
部署成功后，博客地址为：https://z23cc.github.io


## 10. 自动化部署

本项目使用 GitHub Actions 实现完全自动化的部署流程：

### 10.1 部署流程
```
Notion 更新 → GitHub Actions → 同步内容 → 构建 Hexo → 部署到 GitHub Pages
```

### 10.2 触发方式

1. **代码推送触发**（推荐）：
   ```bash
   git push origin main
   ```

2. **手动触发**：
   - GitHub 仓库 → Actions → "Sync and Deploy" → Run workflow

3. **API 触发**（兼容原有方式）：
   ```shell
   https://serverless-api-elog.vercel.app/api/github?user=z23cc&repo=z23cc.github.io&event_type=deploy&token=YOUR_TOKEN
   ```

### 10.3 必要配置

确保以下设置正确配置：

1. **GitHub Pages**：Settings → Pages → Source: GitHub Actions
2. **Actions 权限**：Settings → Actions → General → Read and write permissions
3. **环境变量**：Settings → Secrets → NOTION_TOKEN 和 NOTION_DATABASE_ID

详细设置步骤请参考：[GitHub Pages 设置指南](./GITHUB_PAGES_SETUP.md)


# 自定义 Elog 配置


如果想自定义 Elog 配置，可访问 [Elog 文档](https://elog.1874.cool/)


# 示例

原始示例仓库：[https://github.com/LetTTGACO/notion-hexo](https://github.com/LetTTGACO/notion-hexo)

Notion数据库模版：[elog-hexo-template](https://1874.notion.site/867486af567f4a8897427b15ffd10b3c?v=a25aec8e27d5415e8605e43034f822bd&pvs=4)

本项目博客地址：[https://z23cc.github.io](https://z23cc.github.io)

## 🆚 Vercel vs GitHub Pages

| 特性 | Vercel | GitHub Pages |
|------|--------|--------------|
| 成本 | 免费额度有限 | 完全免费 |
| 配置复杂度 | 零配置 | 需要配置 Actions |
| 构建速度 | 快 | 中等 |
| CDN性能 | 优秀 | 良好 |
| 依赖性 | 依赖第三方 | 只依赖 GitHub |
| 自定义域名 | 支持 | 支持 |

本项目已迁移至 GitHub Pages，享受完全免费的博客托管服务！

