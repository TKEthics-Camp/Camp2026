# The Done-Bar Checklist
# 验收清单

**Day 5, handed out at 9:25.**

"Refine it" is too vague to fill a morning — you'll drift. This is the bar.
Work down the list. Every box is something a real user would notice.

"再改改"这种话太模糊，一个上午会白白流走。这就是标准。
一条条往下走。每一条，真实用户都感觉得到。

---

## Team / 小组: ______________

### It works at all / 基本可用

- [ ] Loads at the live URL — **on a Zhong Gu classroom computer, with no VPN and nobody logged in**
      能在众谷教室的电脑上打开——**没有 VPN，也没有登录任何账号**
- [ ] Shows today's three stories
      能显示今天的三个故事
- [ ] Each story shows where it came from *(Article 3)*
      每个故事都标明了来源 *(第 3 条)*
- [ ] Glossed terms show an explanation
      标注的生词能显示解释
- [ ] **Only approved entries appear** *(Article 6)*
      **只有审核通过的词条才显示** *(第 6 条)*

### The round trip / 数据往返

- [ ] Cast a vote → a new row appears in `votes`
      投一票 → `votes` 表里出现新的一行
- [ ] Submit a take → a new row appears in `takes`
      提交一条观点 → `takes` 表里出现新的一行
- [ ] Refresh the page — still works
      刷新页面 —— 依然正常
- [ ] Open it on a second machine — still works
      换一台电脑打开 —— 依然正常

### The edges (this is where the real bugs live) / 边界情况（真正的 bug 都藏在这里）

- [ ] **Double-click submit — do you get two rows?**
      **连点两下提交——会不会出现两行？**
- [ ] What happens if there are no stories today?
      如果今天没有故事，会怎样？
- [ ] What happens if a take is blank?
      如果观点是空白的，会怎样？
- [ ] What happens if someone writes 2,000 characters?
      如果有人写了两千字，会怎样？
- [ ] What does the screen show while it's loading?
      加载过程中，屏幕上显示什么？

---

## About that double-click / 关于连点两下

You will almost certainly get two rows. **That's your first real engineering bug**,
and it's a good one: it's real, you found it yourself, and fixing it teaches you to
guard against duplicate writes — no abstraction required.

你八成真的会得到两行。**这是你遇到的第一个真正的工程 bug**，而且是个好 bug：
它真实存在，是你自己发现的，修好它就学会了防重复写入——不需要任何抽象概念。

Two ways to fix it. Either is fine:
两种修法，都可以：

1. Disable the button the moment it's clicked, re-enable when the response comes back
   点击的瞬间禁用按钮，等响应回来再恢复
2. Ignore any submit that arrives within a second of the last one
   忽略距离上一次提交不到一秒的请求

---

## The gate / 交付关卡

**11:45 — before lunch.** A TA opens your live URL on a classroom computer.
If it doesn't load, that's what you fix first. Nothing else counts until it does.

**11:45 —— 午餐之前。** 助教会在教室电脑上打开你们的网址。
打不开，就先修这个。在它能打开之前，别的都不算数。
