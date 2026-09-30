# AI Commit Helper

## 功能
一个根据 git 改动自动生成规范 commit message 的工具，提供 CLI + VS Code 插件两种形态。

## 做这个原因
1. 平时改完代码经常复制 diff 到 AI 网页起 commit，重复动作值得工具化 
2. 手写 commit 容易违反团队规范（feat/fix/refactor 前缀经常忘），让工具兜底

## 数据边界
1. 只读 staged diff，未暂存改动不发送
2. API Key 本地存储，不上传 
3. 单次调用只发本次 diff，不发其他文件

## 基本功能（后续需要再补）
1. **核心库**：读 staged diff → 组装 Prompt → 调模型 → 格式校验
2. **CLI 形态**：`aicm` 命令 → 生成 → 交互选择（采用 / 重新生成 / 手动改）→ 提交 
3. **VS Code 插件形态**：源代码管理面板加一个按钮 → 点击生成 → 弹窗确认 → 填入 commit 输入框 
4. **规范约束**：默认 Conventional Commits，支持 `--style` / 配置项切换 
5. **模型配置**：首次运行引导配置 API Key，写入本地配置后自动读取

