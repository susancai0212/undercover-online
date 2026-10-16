# 🎭 谁是内鬼 · 在线多人抽签

## 本地运行
安装 Node.js 20+，在项目目录运行：

```bash
npm install
npm start
```

打开 http://localhost:3000 。

## 部署到 Render
1. 在 GitHub 创建新仓库，将 `package.json`、`server.js` 和 `public/index.html` 上传到仓库根目录。
2. 登录 https://render.com ，选择 New → Web Service，并连接该 GitHub 仓库。
3. Runtime 选择 Node；Build Command 填 `npm install`；Start Command 填 `npm start`。
4. 部署完成后打开 Render 提供的 HTTPS URL。创建房间，复制邀请链接发给朋友。

## 游戏规则
房主设置3–30人的固定总人数。玩家用昵称加入；所有名额满后服务器立即随机分配**恰好一名内鬼**，每个人自行点击抽签才能查看自己的身份。身份仅通过对应玩家的私有 Socket.IO 响应返回。房主可重新开局，所有人身份重新随机分配。

## 注意
- 房间数据只在 Node 服务器内存里；服务重启、休眠或重新部署会清空房间。请在同一局游戏期间保持服务运行。免费托管可能休眠。
- 断线后同一浏览器可用本地保存的随机 token 重连；不要清除浏览器数据。链接只包含房间号，不包含身份或登录 token。
- 本版本适合小型朋友聚会，不含持久化数据库、账号系统、限流或生产级防作弊。请勿用作有奖或涉及真实利益的抽签。
