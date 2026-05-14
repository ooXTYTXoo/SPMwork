# 04 配置管理文档

## 1. 配置项范围

| 编号 | 配置项名称 | 说明 | 存储位置 |
|:---:|:---:|:---|:---|
| CP-01 | README.md | 项目背景、团队分工 | / 根目录 |
| CP-02 | 项目启动说明 | 需求概述、角色分工表 | /docs/01-project-charter.md |
| CP-03 | WBS 文档 | 工作分解结构（至少L3级） | /docs/02-wbs.md |
| CP-04 | 进度计划文档 | 简化进度计划表 | /docs/03-schedule.md |
| CP-05 | 配置管理文档 | 分支策略、合并规则 | /docs/04-config-plan.md |
| CP-06 | 示例代码/资源文件 | 报名/签到核心逻辑示例 | /src/、/assets/ |
| CP-07 | 总结报告 | 实验总结（含冲突解决过程） | /docs/05-summary-report.md |



## 2. 分支策略

| 分支 | 用途 |
|:---:|:---|
| main | 最终发布分支，保存总结报告等终期交付物 |
| dev | 开发集成分支，合并各 feature 完成的功能 |
| feature-* | 单一功能开发 |


## 3. 命名约定
文档命名
| 文档类型 | 命名格式 | 示例 |
|:---:|:---|:---|
| WBS 文档 | WBS_v<版本>.md | WBS_v1.0.md |
| 进度计划 | Schedule_v<版本>.md | Schedule_v1.0.md |
| 总结报告 | Summary_<日期>.md | Summary_20250630.md |
| 配置管理文档 | ConfigPlan_v<版本>.md | ConfigPlan_v1.0.md |
| 变更记录 | changelog.md（持续更新） | /docs/cm/changelog.md |

分支命名
| 分支类型 | 格式 | 示例 |
|:---:|:---|:---|
| 功能分支 | feature/<功能模块> | feature/summary-report |
| 修复分支 | hotfix/<问题描述> | hotfix/fix-conflict |
## 4. 合并规则
合并规则
feature-* → dev	开发人员自合并

dev → main	项目经理

冲突处理流程

第1步：git pull origin <目标分支>        → 拉取最新代码

第2步：手动逐文件解决冲突                → 保留双方修改

第3步：运行测试确保无回归                 → 示例代码可编译/运行

第4步：git add . && git commit           → 重新提交并注明"解决冲突"

第5步：push 并完成 PR                      → 通知 Reviewer 重新 Review

## 5. 版本留痕

冲突解决记录	完整 commit 记录 + 总结报告中说明

总结报告	提交至 main 分支，打 Tag v1.0.0-release
