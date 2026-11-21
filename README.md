# 2026-11-07-00-00-40

GitHub 仓库：`https://github.com/hexi9966/2026-11-07-00-00-40`（Public）

## GitHub 调取工具

`tools/gh-fetch.sh` — 从 GitHub 拉取任意公开仓库到本工作区。

走 `api.github.com` zipball 通道，绕开本地代理对 `git clone` 的间歇性 502。

### 用法

```bash
./tools/gh-fetch.sh <owner/repo> [branch] [目标目录]
```

- `branch` 留空 → 自动用仓库默认分支
- 目标目录留空 → `./<owner>_<repo>`

### 示例

```bash
./tools/gh-fetch.sh skale-me/skale
./tools/gh-fetch.sh skalesapp/skales main ./skales
./tools/gh-fetch.sh skalenetwork/skale-network
```

### 依赖

- `gh` CLI：`C:\Users\18899\.workbuddy\binaries\gh\bin\gh.exe`
- Token：从台账 D-1 段自动读取，或用 `GH_TOKEN` 环境变量覆盖
- Python 3（解压 + 校验）

### 已验证

| 仓库 | 分支 | 结果 |
|---|---|---|
| `skale-me/skale` | master | 216 项，OK |
| `skalesapp/skales` | main | 24 项，OK |
| `skalenetwork/skale-network` | master | 可拉取 |
