# GitHub Pages 部署指南

由于系统限制，我已将代码推送到分支 `claude/warhammer-40k-carousel-011CUMeL4m6A1p5QGTzeKKGc`。

你需要在GitHub上手动配置GitHub Pages。以下是详细步骤：

## 配置步骤

### 方法一：直接从现有分支发布（推荐）

1. **打开你的GitHub仓库**
   - 访问：`https://github.com/CalvinoShaw/-`

2. **进入Settings**
   - 点击仓库顶部的 **Settings** 标签

3. **找到Pages设置**
   - 在左侧菜单中找到 **Pages** 选项（在 Code and automation 部分）

4. **配置Source**
   - 在 "Build and deployment" 部分
   - **Source**: 选择 "Deploy from a branch"
   - **Branch**: 选择 `claude/warhammer-40k-carousel-011CUMeL4m6A1p5QGTzeKKGc`
   - **Folder**: 选择 `/ (root)`
   - 点击 **Save** 按钮

5. **等待部署**
   - GitHub会自动开始部署
   - 通常需要1-3分钟
   - 刷新页面后，你会看到一个绿色的提示框显示部署成功的URL

6. **访问你的网站**
   - URL格式通常是：`https://calvinoshaw.github.io/-/`
   - 或者GitHub会在Pages设置页面显示具体的URL

### 方法二：创建main分支（需要仓库管理员权限）

如果你有仓库管理员权限，可以手动创建main分支：

1. 在GitHub仓库页面，点击分支下拉菜单
2. 在 `claude/warhammer-40k-carousel-011CUMeL4m6A1p5QGTzeKKGc` 分支上
3. 点击 "View all branches"
4. 找到该分支，点击旁边的三个点菜单
5. 选择 "Set as default branch" 或创建一个新的main分支
6. 然后在Pages设置中选择main分支

### 方法三：使用GitHub CLI（如果已安装）

如果你本地安装了GitHub CLI (`gh`命令)，可以尝试：

```bash
# 在本地创建main分支
git checkout -b main
git push origin main

# 然后通过GitHub网页配置Pages
```

## 验证部署

部署完成后：
1. 访问提供的URL
2. 你应该能看到战锤40K图片轮播页面
3. 图片会每3秒自动切换
4. 100张图片随机播放

## 常见问题

### 1. 404错误
- 等待3-5分钟，GitHub需要时间构建和部署
- 确认分支选择正确
- 确认选择了 `/ (root)` 文件夹

### 2. 图片无法加载
- 这是正常的，因为使用的是第三方图片API
- 某些图片可能因网络问题无法加载
- 系统会自动使用占位符图片

### 3. 找不到Pages设置
- 确保你有仓库的管理员权限
- 如果是私有仓库，可能需要GitHub Pro账户

## 需要帮助？

如果遇到问题：
1. 确认你有仓库的Settings访问权限
2. 检查分支名称是否正确复制
3. 查看GitHub的部署日志（在Pages设置页面的最下方）

---

部署成功后，你就可以通过链接直接访问你的战锤40K轮播网页了！

⚔️ **For the Emperor!** ⚔️
