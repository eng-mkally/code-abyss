# Skills 知识域覆盖补全计划

## 现状分析

### 已有域（7个，40个文档）
| 域 | 文档数 | 覆盖度 | 评估 |
|----|--------|--------|------|
| security | 6 | ⭐⭐⭐⭐ | 攻防完整，缺威胁建模/供应链安全 |
| development | 7 | ⭐⭐⭐ | 主流语言覆盖，缺 PHP/Swift/Kotlin |
| architecture | 7 | ⭐⭐⭐⭐ | 架构模式完整，缺微服务治理/事件溯源 |
| devops | 7 | ⭐⭐⭐⭐ | DevOps 完整，缺容器编排细节/GitOps |
| ai | 2 | ⭐⭐ | 基础覆盖，缺 RAG/Prompt工程/模型评估 |
| frontend-design | 3 | ⭐⭐⭐ | UI/UX 基础，缺状态管理/性能优化 |
| orchestration | 2 | ⭐⭐⭐ | 多Agent协同完整 |

### 官方 Skill 规范要点（来源：https://code.claude.com/docs/en/skills）

**核心要素**：
1. **YAML frontmatter** — name/description/disable-model-invocation/user-invocable/allowed-tools/context/agent
2. **Markdown 内容** — 指令/模板/示例/检查清单
3. **支持文件** — 模板/示例/脚本（可选）
4. **动态上下文** — `!`command`` 语法注入实时数据
5. **子 Agent 执行** — `context: fork` + `agent: Explore/Plan`

**最佳实践**：
- Description 清晰描述使用场景（触发词）
- 区分 Reference（知识）vs Task（任务）
- SKILL.md < 500 行，详细内容拆分到支持文件
- 使用 `$ARGUMENTS` / `$0` / `$1` 接收参数
- 生成可视化输出（HTML/图表）

## 覆盖缺口分析

### 1. 语言/框架缺口（development 域）
**缺失**：
- PHP（Laravel/Symfony）
- Swift（iOS 开发）
- Kotlin（Android 开发）
- Dart（Flutter）
- Elixir（Phoenix）
- Scala（Akka）

**优先级**：PHP > Swift/Kotlin > Dart

### 2. 前端生态缺口（frontend-design 域）
**缺失**：
- 状态管理（Redux/Zustand/Jotai）
- 性能优化（懒加载/代码分割/虚拟滚动）
- 构建工具（Vite/Webpack/Turbopack）
- 测试（Vitest/Playwright/Cypress）
- SSR/SSG（Next.js/Nuxt/Astro）

**优先级**：状态管理 > 性能优化 > 测试

### 3. AI/LLM 缺口（ai 域）
**缺失**：
- RAG 系统设计（检索/重排/生成）
- Prompt 工程（Few-shot/CoT/ReAct）
- 模型评估（RAGAS/LLM-as-Judge）
- 向量数据库（Pinecone/Weaviate/Qdrant）
- LLM 应用架构（缓存/流式/重试）

**优先级**：RAG > Prompt工程 > 模型评估

### 4. 云原生/基础设施缺口（新域：infrastructure）
**缺失**：
- Kubernetes 运维（Helm/Kustomize/Operator）
- 服务网格（Istio/Linkerd）
- GitOps（ArgoCD/Flux）
- IaC（Terraform/Pulumi/CDK）
- 容器安全（镜像扫描/运行时防护）

**优先级**：Kubernetes > GitOps > IaC

### 5. 数据工程缺口（新域：data-engineering）
**缺失**：
- 数据管道（Airflow/Dagster/Prefect）
- 数据仓库（Snowflake/BigQuery/Redshift）
- 流处理（Kafka Streams/Flink）
- 数据质量（Great Expectations/dbt）
- ETL/ELT 模式

**优先级**：数据管道 > 流处理 > 数据质量

### 6. 安全深化缺口（security 域扩展）
**缺失**：
- 威胁建模（STRIDE/PASTA）
- 供应链安全（SBOM/依赖扫描）
- 密钥管理（Vault/KMS）
- 零信任架构（BeyondCorp）
- 安全编码（OWASP Top 10 防御）

**优先级**：威胁建模 > 供应链安全 > 密钥管理

### 7. 移动开发缺口（新域：mobile）
**缺失**：
- iOS 开发（SwiftUI/UIKit）
- Android 开发（Jetpack Compose/Kotlin）
- 跨平台（React Native/Flutter）
- 移动安全（证书锁定/混淆）
- 移动 CI/CD（Fastlane/Bitrise）

**优先级**：跨平台 > iOS > Android

### 8. 测试工程缺口（devops 域扩展）
**缺失**：
- 测试策略（测试金字塔/测试左移）
- E2E 测试（Playwright/Cypress）
- 性能测试（k6/JMeter）
- 混沌工程（Chaos Mesh/Gremlin）
- 测试数据管理

**优先级**：测试策略 > E2E测试 > 性能测试

## 补全优先级（按紧迫性排序）

### P0（立即补全）— 高频需求
1. **AI/LLM 扩展**（ai 域）
   - RAG 系统设计
   - Prompt 工程
   - 模型评估

2. **前端生态**（frontend-design 域）
   - 状态管理
   - 性能优化
   - 测试

3. **语言扩展**（development 域）
   - PHP（Laravel）
   - Swift（iOS）
   - Kotlin（Android）

### P1（近期补全）— 中频需求
4. **云原生基础设施**（新域：infrastructure）
   - Kubernetes 运维
   - GitOps
   - IaC

5. **安全深化**（security 域）
   - 威胁建模
   - 供应链安全
   - 密钥管理

6. **测试工程**（devops 域）
   - 测试策略
   - E2E 测试
   - 性能测试

### P2（长期补全）— 低频需求
7. **数据工程**（新域：data-engineering）
   - 数据管道
   - 流处理
   - 数据质量

8. **移动开发**（新域：mobile）
   - 跨平台
   - iOS/Android

## 实施计划

### 阶段 1：AI/LLM 扩展（3个文档）
```
skills/domains/ai/
├── rag-system.md          # RAG 架构/检索/重排/生成
├── prompt-engineering.md  # Few-shot/CoT/ReAct/模板
└── model-evaluation.md    # RAGAS/LLM-as-Judge/指标
```

### 阶段 2：前端生态（3个文档）
```
skills/domains/frontend-design/
├── state-management.md    # Redux/Zustand/Jotai/Context
├── performance.md         # 懒加载/代码分割/虚拟滚动/优化
└── testing.md             # Vitest/Playwright/测试策略
```

### 阶段 3：语言扩展（3个文档）
```
skills/domains/development/
├── php.md                 # Laravel/Symfony/Composer
├── swift.md               # SwiftUI/UIKit/Combine
└── kotlin.md              # Jetpack Compose/Coroutines
```

### 阶段 4：云原生基础设施（新域，3个文档）
```
skills/domains/infrastructure/
├── SKILL.md
├── kubernetes.md          # Helm/Kustomize/Operator
├── gitops.md              # ArgoCD/Flux/声明式部署
└── iac.md                 # Terraform/Pulumi/CDK
```

### 阶段 5：安全深化（3个文档）
```
skills/domains/security/
├── threat-modeling.md     # STRIDE/PASTA/攻击树
├── supply-chain.md        # SBOM/依赖扫描/签名验证
└── secrets-management.md  # Vault/KMS/轮转策略
```

### 阶段 6：测试工程（3个文档）
```
skills/domains/devops/
├── testing-strategy.md    # 测试金字塔/测试左移/契约测试
├── e2e-testing.md         # Playwright/Cypress/可视化回归
└── performance-testing.md # k6/JMeter/负载/压力测试
```

## 质量标准

每个文档必须包含：
1. **场景触发词** — description 中明确使用场景
2. **代码片段** — 至少 3 个实用代码示例
3. **最佳实践** — 经验总结/反模式警告
4. **检查清单** — 可执行的审查要点
5. **参考资源** — 官方文档/工具链接

每个文档控制在 **200-400 行**，超过则拆分到支持文件。

## 执行策略

- **批量生成** — 每次 3-6 个文档，使用 multi-agent 并行
- **模板驱动** — 建立统一模板，确保结构一致
- **渐进验证** — 每批完成后验证触发词和代码可用性
- **社区反馈** — 根据实际使用调整优先级

## 参考资源

- [Claude Code Skills 官方文档](https://code.claude.com/docs/en/skills)
- [Agent Skills 开放标准](https://agentskills.io)
- [Skills 最佳实践](https://mikhail.io/2025/10/claude-code-skills/)
