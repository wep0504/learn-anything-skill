# learn-anything

把 AI 助手变成一套有状态的学习系统，而不是答案贩卖机。

真实学习需要四个要素：**一条路径、一次测试、一次压缩、一个反馈循环**。普通 AI 对话通常一个都不具备。这个 skill 把它们组织成六个可组合的阶段，并把学习成果持久化到磁盘，让下次对话可以接着学。

## 六个阶段

| 阶段 | 作用 | 产物 |
| --- | --- | --- |
| 学习阶梯 | 5 个难度等级，每级带里程碑、练习、常见错误、自检题 | `ladder.md` |
| 20 小时计划 | 找出带来 80% 结果的 20% 核心，排成 10 个 2 小时 session | `plan.md` |
| 考到我崩溃 | 严格考官，10 题逐级加难，一次一题，逐题打分找漏洞 | `progress.md` |
| 一页速查表 | 压缩到 5 分钟能复习完的单页 | `cheatsheet.md` |
| 噪声中的信号 | 只选 5 个最高杠杆资源，排出 7 天路径 | `resources.md` |
| 费曼循环 | 讲给 12 岁小孩 → 用户复述 → 只补漏洞 → 重复 | `notes.md` |

## 安装

### Claude Code

```bash
cp -r learn-anything ~/.claude/skills/
```

### DeepSeek Harness

```bash
cp -r learn-anything ~/.agents/skills/
```

DSH 也支持项目级安装：`<project>/.agents/skills/` 或 `<project>/.dsh/skills/`。

### 分发文件

`dist/learn-anything.skill` 是打包好的可分发包，解压到对应 skills 根目录即可。

## 使用

直接说出学习意图即可自动触发：

- 「我想从零学 Rust，每周 10 小时」
- 「SQL 窗口函数我看了教程感觉懂了，但一写就卡」
- 「我好像懂了但讲不出来」
- 「继续学 <主题>」

学习产物会写入当前工作目录的 `learning/<主题>/`。

## 设计要点

- **一次只推进一问**：主动回忆比被动阅读有效，一次性抛出 10 道题会让测试失效。
- **答完之前不公布答案**：哪怕显得「不够 helpful」。
- **按需缩放**：单点概念问题走轻量模式，不启动完整六阶段流程。
- **资源必须真实**：不确定的书名、课程、链接会明确标注，避免编造。

## 来源

方法论整理自 Rahul（[@sairahul1](https://x.com/sairahul1)）的文章 *How To Learn Anything 10x Faster Using Claude*。本仓库是其 Claude Code / DeepSeek Harness skill 实现。

## License

[MIT](LICENSE) © 2026 wep0504
