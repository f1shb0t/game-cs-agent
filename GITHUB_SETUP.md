# GitHub 仓库设置指南

由于 GitHub CLI 需要身份认证，请按照以下步骤手动创建 GitHub 仓库并推送代码。

## 选项 1: 使用 GitHub CLI (推荐)

```bash
# 1. 认证 GitHub CLI
gh auth login

# 2. 创建仓库并推送
gh repo create game-cs-agent \
  --public \
  --description "游戏智能客服 Demo - 基于 AWS Bedrock 和 Strands Agent 的 AI 客服系统" \
  --source=. \
  --remote=origin \
  --push
```

## 选项 2: 使用 Git + GitHub Web

### 步骤 1: 在 GitHub 网站创建仓库

1. 访问 https://github.com/new
2. 仓库名: `game-cs-agent`
3. 描述: `游戏智能客服 Demo - 基于 AWS Bedrock 和 Strands Agent 的 AI 客服系统`
4. 选择 **Public**
5. **不要** 初始化 README、.gitignore 或 license
6. 点击 "Create repository"

### 步骤 2: 推送本地代码

```bash
# 添加远程仓库（替换 YOUR_USERNAME 为你的 GitHub 用户名）
git remote add origin https://github.com/YOUR_USERNAME/game-cs-agent.git

# 推送代码
git branch -M main
git push -u origin main
```

## 选项 3: 使用 SSH

如果你已经配置了 SSH 密钥：

```bash
# 在 GitHub 创建仓库后，添加远程仓库
git remote add origin git@github.com:YOUR_USERNAME/game-cs-agent.git

# 推送代码
git branch -M main
git push -u origin main
```

## 验证

推送成功后，访问你的仓库：
```
https://github.com/YOUR_USERNAME/game-cs-agent
```

应该能看到所有文件和完整的 README。

## 下一步

仓库创建成功后，可以：

1. ⭐ 给仓库加星标
2. 📝 在 GitHub Issues 中记录改进想法
3. 🔗 分享给其他人
4. 🚀 开始部署：运行 `./deploy.sh`
