# Brown Dust 2 自动化工具

一个 OpenClaw Skill，帮助布朗Dust2玩家自动完成每日签到和兑换码兑换。

## 功能

- ✅ 每日自动签到（网页商店）
- ✅ 自动检查并兑换最新兑换码（BD2Pulse）

## 安装

### 方式1：ClawHub（推荐）
```bash
clawhub install browndust2
```

### 方式2：手动安装
```bash
git clone https://github.com/your-repo/openclaw-skill-browndust2.git ~/.openclaw/workspace/skills/browndust2
```

## 使用前准备

1. **打开浏览器登录一次**（仅首次）：
   ```bash
   browser start --profile openclaw
   ```
   
2. 访问以下网址并登录：
   - [网页商店](https://webshop.browndust2.global/CT/)
   - [BD2Pulse](https://thebd2pulse.com/zh-CN/)

3. 保持浏览器登录状态（不要清除缓存）

## 使用方法

### 签到
让 Agent 执行：
> 请帮我签到 Brown Dust 2

### 兑换兑换码
让 Agent 执行：
> 请帮我兑换 Brown Dust 2 兑换码，昵称是"你的游戏昵称"

## 定时任务（可选）

如果需要每天自动执行，可以设置 Cron：

```bash
# 每天早上8点签到
openclaw cron add --name "BD2签到" --cron "0 8 * * *" --message "请帮我签到Brown Dust 2" --channel discord --to "你的ID" --expect-final

# 每天早上8点30兑换码
openclaw cron add --name "BD2兑换码" --cron "30 8 * * *" --message "请帮我兑换Brown Dust 2兑换码，昵称是你的昵称" --channel discord --to "你的ID" --expect-final
```

## 故障排除

- **登录失效**：需要重新在浏览器登录
- **兑换失败**：某些码可能已经兑换过，这是正常的

## 发布更新

```bash
cd ~/.openclaw/workspace/skills/browndust2
git add .
git commit -m "更新说明"
git push
clawhub publish
```

## License

MIT