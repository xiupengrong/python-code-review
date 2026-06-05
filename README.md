# Python 全维度代码审查 Skill

> Claude Code 插件 — 对 Python 项目进行 9 维度系统性代码审查，内置金融安全规范检测，生成聚焦改进和优化的中文报告。

## ✨ 功能特性

> 🆕 **v1.1.0 新增金融安全规范检测**：自动识别金融类项目，在安全性维度中激活专项检查——覆盖金额计算精度、事务完整性、审计追踪、支付安全、反欺诈风控、对账机制、合规要求等 8 大检查领域。

覆盖 **9 个关键维度** 的深度审查：

| # | 维度 | 关注点 |
|---|------|--------|
| 1 | 架构设计 | 目录结构、依赖方向、关注点分离、设计模式 |
| 2 | 安全性 | 注入防护、敏感信息、加密实践、动态执行、**金融安全规范** |
| 3 | 可读性 | PEP 8、命名规范、类型注解、文档字符串 |
| 4 | 健壮性 | 异常处理、资源管理、并发安全、边界条件 |
| 5 | 可扩展性 | 开闭原则、依赖注入、插件化、配置驱动 |
| 6 | 性能与效率 | 算法选择、异步优化、缓存策略、N+1 查询 |
| 7 | 测试与质量保障 | 单元/集成测试覆盖、CI 流水线 |
| 8 | 依赖与部署 | 依赖管理、虚拟环境、Docker 镜像 |
| 9 | 文档记录 | README 完整性、设计决策记录、API 文档 |

输出结构化中文 Markdown 审查报告，包含优先改进建议、各维度详细发现和代码优化亮点。

## 📦 安装

### 方式一：通过 Claude Code 命令安装（推荐）

在 Claude Code 中依次执行两步：

**第一步：添加市场源**

```
/plugin marketplace add xiupengrong/python-code-review
```

**第二步：安装插件**

```
/plugin install python-code-review
```

### 方式二：手动安装

1. 克隆仓库到 Claude Code 插件目录：

```bash
# Windows
git clone https://github.com/xiupengrong/python-code-review.git "%USERPROFILE%\.claude\plugins\marketplaces\python-code-review"

# macOS / Linux
git clone https://github.com/xiupengrong/python-code-review.git ~/.claude/plugins/marketplaces/python-code-review
```

2. 在 Claude Code 中通过 `/plugin` 命令管理并启用插件

## 🚀 使用方法

安装后，在 Claude Code 中直接用自然语言触发审查：

```
帮我审查一下这个 Python 项目
```

```
对 src/ 目录做一次代码审查
```

```
检查一下这个项目的安全性和性能
```

Skill 会自动识别 Python 代码审查意图并启动 9 维度系统审查。

## 📄 报告示例

审查报告包含：

- **项目概览** — 项目类型、文件数、代码行数
- **优先改进建议** — 按 P0（立即修复）→ P3（锦上添花）分级，附具体代码对比
- **详细发现** — 每个维度的亮点和改进优化点（含具体文件路径和行号）
- **金融安全合规**（如适用）— 金额精度、事务完整性、审计追踪、支付安全等专项检查
- **优化亮点** — 总结项目中的优秀实践和值得推广的模式

## 📁 项目结构

```
python-code-review/
├── .claude-plugin/
│   ├── plugin.json              # 插件清单
│   └── marketplace.json         # 市场注册信息
├── skills/
│   └── python-code-review/
│       ├── SKILL.md             # Skill 定义（审查流程和指令）
│       └── references/
│           └── checklist.md     # 9 维度详细检查项清单
├── LICENSE
└── README.md
```

## 🏦 金融项目审查

当检测到项目涉及支付、转账、账户管理等金融业务时，Skill 会自动在安全性维度中激活金融安全规范检查，覆盖：

- **金额计算精度** — `Decimal` vs `float`，舍入规则
- **事务完整性** — ACID、幂等性、分布式事务
- **金融数据保护** — PCI DSS、字段级加密、脱敏存储
- **审计追踪** — 不可变日志、操作溯源
- **反欺诈与风控** — 频率限制、规则引擎、异常拦截
- **支付安全** — 令牌化、状态机、签名验证
- **对账与职责分离** — Maker-Checker、多级审批
- **合规要求** — KYC/AML、数据保留、监管报送

## 📝 许可证

[MIT](LICENSE)
