# 發布指南

準備工作已完成，可以開始發布 Agent IDE。

## 快速發布

### 發布到 npm

```bash
# 登入 npm
npm login

# 發布
npm publish --access public

# 驗證
npm view agent-ide
```

發布後使用者可以：
```bash
npm install -g agent-ide
```

### 提交到 MCP Registry

1. Fork https://github.com/modelcontextprotocol/servers
2. 參考 `.github/MCP_REGISTRY_SUBMISSION.md` 建立 PR
3. 等待審核

### 驗證安裝

```bash
# npm 安裝測試
npm install -g agent-ide
agent-ide --version
agent-ide-mcp

# Claude Code 整合測試
claude mcp add agent-ide npx -y https://github.com/vivalalova/agent-ide.git agent-ide-mcp
```

重新啟動 Claude Code，輸入「請列出所有可用的 agent-ide 工具」驗證。

## 已準備的檔案

✅ `mcp.json` - MCP 設定
✅ `.npmignore` - npm 排除清單
✅ `package.json` - 完整發布資訊
✅ `PUBLISH_CHECKLIST.md` - 詳細檢查清單
✅ `.github/MCP_REGISTRY_SUBMISSION.md` - MCP PR 文件

## 發布後連結

- npm 套件：https://www.npmjs.com/package/agent-ide
- GitHub：https://github.com/vivalalova/agent-ide
- Issues：https://github.com/vivalalova/agent-ide/issues
- Discussions：https://github.com/vivalalova/agent-ide/discussions

## 注意事項

### npm 發布

- 首次發布需要 `--access public`
- 版本號無法重複使用
- 發布後 24 小時內可以 unpublish

### MCP Registry

- 需要維護者審核 PR
- 確保所有測試通過
- 文件要清楚完整

## 發布後

### 建立 GitHub Release

```bash
git tag -a v0.1.0 -m "Release v0.1.0"
git push origin v0.1.0
```

然後在 GitHub 上建立 Release。

### 更新版本

下次更新時：
1. 更新版本號：`package.json`, `mcp.json`
2. 執行檢查清單
3. 發布：`npm publish`
4. 更新 MCP Registry（如有需要）

---

**準備好了嗎？開始發布吧！** 🚀

詳細檢查清單請查看 [PUBLISH_CHECKLIST.md](./PUBLISH_CHECKLIST.md)
