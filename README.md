# AI TestCraft

AI 测试与工程实验室：整理大模型评测、RAG 示例和自动化测试实践。

## 从这里开始

| 模块 | 已有内容 | 入口 |
|---|---|---|
| 大模型测试框架 | Pytest、JSON 驱动用例、关键词与语义评估、准确性／鲁棒性／格式／RAG 检查 | [testai](testai/README.md) |
| RAG 示例 | 文档检索、向量存储与问答示例，包含命令行和 Web 入口 | [rag_example](rag_example/README.md) |
| 硬件测试脚本 | SSH 调度、FIO／iperf、日志收集与报告生成 | [auto_hardware_test](auto_hardware_test/README.md) |
| 学习资料 | Agent 测试与 JMeter 相关笔记和配置 | [文档](文档/) |

这是多个历史实验模块的集合，各模块单独配置和运行。

## 大模型测试快速开始

在仓库根目录执行，先运行 Mock 测试子集：

```bash
cd testai
python -m venv .venv
# 激活虚拟环境后执行：
python -m pip install -r requirements.txt
python -m pytest tests/test_accuracy.py tests/test_robustness.py tests/test_format.py tests/test_rag.py -v
```

真实 API 和 Coze 测试需自行配置服务与凭据，可能产生调用费用；详见模块说明，不应混入离线结果。

RAG 示例从 [安装与运行说明](rag_example/README.md) 开始，复制 `.env.example` 为本地 `.env` 后填写自己的配置。示例配置不包含可用密钥。

硬件模块会通过 SSH 执行压测、部署或磁盘相关命令，运行前需核对脚本及目标，仅在自己的隔离实验环境使用。

## 验证与项目边界

- 本次工作完成仓库导航、命名与当前版本配置整理，未重跑历史模块，也未调用真实大模型或执行硬件压测。
- 历史文档中的用例数量、通过率与准确率不代表当前版本实测结果；需要按具体版本、数据集、运行命令与报告重新确认。
- Mock 通过只能说明该测试路径的行为；真实模型效果需要单独评估。

## 配置与贡献

仅提交空白配置示例，真实密钥、服务器密码、内部地址和客户数据保留在本地；缓存、日志、向量库和 IDE 文件不进入新提交。

当前版本移除 `.env` 并替换检测到的配置凭据。历史 Git 提交可能仍保留旧值，原凭据需要在提供方作废或轮换；本次未改写历史。

新增模块请补充：解决的问题、运行步骤、虚构数据示例、验证证据与限制。项目总入口见 [AI 与测试工程作品集](https://github.com/test123604/ai-project-portfolio)。
