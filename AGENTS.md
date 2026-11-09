# AGENTS.md

本文件记录本仓库对 AI 编码助手的约定。修改前请先阅读。

## 提交约定（重要）

**每完成一个阶段性的改动，必须立刻提交一次。** 不要攒到最后一次性提交，也不要把不相关的改动混在同一个提交里。

- 一个阶段 = 一个可独立描述的、能说清「做了什么、为什么」的改动单元
- 例如：新增一个模块、修好一个 bug、调整一处配置、重构一个文件
- 提交信息用简洁的祈使句概括该阶段，例如 `feat: 增加用户登录接口`、`fix: 修正配置路径解析`

标准流程：

```bash
git add -A          # 或只 add 本阶段涉及的文件
git commit -m "..." # 描述本阶段改动
git push            # 保持与 origin/main 同步
```

提交前先跑 `git status`，确认没有被误纳入的临时文件、密钥或大文件。

## 分支与远端

- 主分支：`main`
- 远端：`origin` → `https://github.com/WLFS5998/git.git`
- 直接向 `main` 提交，除非用户另有要求

## 环境说明

- Git 可执行文件位于 `F:\Git\cmd\git.exe`
- 若当前终端提示找不到 `git`，先执行：`$env:Path = "F:\Git\cmd;" + $env:Path`
- 直连 `github.com:443` 会被阻断，本机代理为 `127.0.0.1:7890`。本仓库已配置
  `http.proxy` / `https.proxy` 指向该代理；若推送报 `Connection was reset`，
  先确认代理是否在运行

## 不要提交的内容

见 `.gitignore`。特别地：不要提交 `.env`、密钥、令牌、`node_modules/`、构建产物。
