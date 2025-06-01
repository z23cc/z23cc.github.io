# 段舸的博客

基于 Notion + Hexo + GitHub Pages 的个人博客

## 技术栈

- Notion（写作） + Hexo（生成） + GitHub Pages（部署）
- 主题：Butterfly
- 自动同步：Elog + GitHub Actions

## 快速开始

1. **Fork 仓库**：[点击 Fork](https://github.com/elog-x/notion-hexo/fork)

2. **安装依赖**：
   ```bash
   npm install
   ```

3. **配置 Notion**：
   - 复制 `.elog.example.env` 为 `.elog.env`
   - 填入 Notion Token 和 Database ID

4. **本地调试**：
   ```bash
   npm run sync:local  # 同步 Notion 内容
   npm run server      # 启动本地服务
   ```

5. **部署**：推送代码到 GitHub，自动部署


## GitHub Pages 配置

1. **启用 Pages**：Settings → Pages → Source: GitHub Actions
2. **设置权限**：Settings → Actions → General → Read and write permissions
3. **添加密钥**：Settings → Secrets → 添加 `NOTION_TOKEN` 和 `NOTION_DATABASE_ID`

## 自动部署

- **定时同步**：每天4次自动构建（8:00、12:00、18:00、22:00）
- **手动触发**：推送代码或在 Actions 页面手动运行
- **访问地址**：https://z23cc.github.io


## 参考资源

- [Elog 文档](https://elog.1874.cool/)
- [原始模板](https://github.com/LetTTGACO/notion-hexo)
- [Notion 数据库模版](https://1874.notion.site/867486af567f4a8897427b15ffd10b3c?v=a25aec8e27d5415e8605e43034f822bd&pvs=4)

