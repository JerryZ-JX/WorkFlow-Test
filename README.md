
### 拆解任务
1. 找会计准则案例 Skill:test-get-news
2. 根据会计准则案例生成案例报告 Skill:test-create-report
3. 根据案例报告，做文案选题 Skill:test-create-topics
4. 根据文案选题，生成文案 Skill:test-write-scipts。写作时参考 [stipulate/文案样稿-活泼版.md](stipulate/文案样稿-活泼版.md) 的内容和表达方式，并结合对应选题及案例资料核对事实。

### WorkFlow
1. 拆任务
2. 提要求，审结果，编写规范，限制AI输出的内容。
3. 把刚才的任务打包成skill
4. 调度skill: workflow
5. 创建两个状态文件：state.json, log.md

完整流程现由 `news-workflow` Skill 串联；也可从已有阶段继续。模板 `stipulate/准则案例模板.md` 只保留四列格式，已收集的案例保存在 `news`，不要将模板内容当作新案例。每次运行前检查同日已有成果；另一批收集使用连续批次号，沿用到报告、选题和文案。

执行时创建或更新 `state.json` 与 `log.md`：前者记录批次、各阶段文件与状态、待核实事项，后者追加本次核实和修改记录。新核实的资料若改变案例事实，需要同步检查受影响的后续成果。

