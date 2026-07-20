# Backend Connection Card
# 后端接入卡

**Day 4, 10:20–10:40.** Do this **before** you write any product code.
**第四天上午。** 在写任何产品代码**之前**完成这一步。

---

## The architecture in one picture / 架构一览

```
飞书多维表格 (Feishu Bitable)          ← teacher writes stories, approves glossary
        │                                 老师在这里写故事、审核生词
        │  TA exports once a day
        ▼
   data.json  (a plain file in your repo)  ← your app READS this
        │                                     应用从这里读取
        ▼
   your app  ─── POST ──▶  camp write API  ──▶  votes / takes tables
   你的应用                  营地写入接口              投票 / 观点
```

**Two rules that explain the whole design:**

- **Reads need no server.** Stories change once a day, so we precompute them into a
  static file. No API, no login, no CORS — and it loads fast on a weak connection.
- **Only writes need a server.** Votes and takes happen constantly and unpredictably,
  so those go through a real API.

> **This is a genuine architecture lesson:** precompute what rarely changes; only call
> a server for what does. It is the single decision that makes this app work in a
> village classroom.
>
> **这是一条真正的架构原则：** 很少变的东西，提前算好存成文件；只有真正会变的，
> 才去请求服务器。正是这个决定，让你的应用能在村小的电脑上跑起来。

---

## Step 1 · Read the stories / 读取故事

Your app fetches one file. That's it.

```js
// Load today's stories and approved glossary
async function loadData() {
  const res = await fetch('./data.json');
  const data = await res.json();
  return data;               // { stories: [...], glossary: [...] }
}
```

**Shape of `data.json`:**

```json
{
  "date": "2026-07-21",
  "stories": [
    {
      "story_id": "s1",
      "title": "...",
      "body": "...",
      "source_name": "Reuters",
      "source_url": "https://..."
    }
  ],
  "glossary": [
    {
      "story_id": "s1",
      "term": "tariff",
      "explanation": "A tax a country charges on goods bought from another country.",
      "status": "approved"
    }
  ]
}
```

⚠️ **Only entries with `status: "approved"` are ever exported.** That's Constitution
Article 6, enforced by the pipeline rather than by hope.
**只有 `status: "approved"` 的词条才会被导出**——宪法第 6 条，由流程保证，而不是靠自觉。

---

## Step 2 · Write a vote / 写入投票

```js
const API = 'PASTE_THE_CAMP_API_URL_HERE';

async function castVote(storyId, student, choice) {
  const res = await fetch(API + '/records', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      table: 'votes',
      record: { story_id: storyId, student: student, choice: choice }
    })
  });
  return res.json();
}
```

Takes use the **identical** mechanism — just `table: 'takes'` and a `take_text` field.
Don't build takes until voting works end to end.

观点（takes）用的是**完全一样**的机制，只是把表名换成 `takes`。
投票没跑通之前，不要动观点功能。

---

## Step 3 · SMOKE TEST — do this before anything else
## 第三步 · 冒烟测试——务必先做这一步

**Test 1 — can you read?**
Open `data.json` directly in your browser. Do you see today's stories?
直接在浏览器里打开 `data.json`，能看到今天的故事吗？

**Test 2 — can you write?**
Run `castVote('TEST', 'SMOKE', 'agree')` from the console. Does a new row appear in
the projected table?
在控制台运行一次测试投票，投屏的表格里有没有出现新的一行？

### 🛑 If either test fails, STOP.
### 🛑 任何一个测试没通过，立刻停下。

Everything you build on top of a broken pipe is wasted time. Get a TA.
在一条不通的管道上盖东西，全都是白费功夫。叫助教。

---

## When it goes wrong / 出问题时

| Symptom / 现象 | Likely cause / 可能原因 |
|---|---|
| `data.json` 404s | Wrong path. It must sit next to `index.html`. Use `./data.json` |
| Stories load but glossary is empty | Nothing has been **approved** yet — that's the review gate working |
| POST returns nothing, no error | Check the API URL. A silent failure usually means a wrong or missing endpoint |
| Works on your laptop, not in the classroom | The classroom has **no VPN**. Test on the actual machine, not yours |
| Two rows appear for one click | You double-clicked. **That's your first real bug** — go fix it |

---

## 🪂 Parachute / 兜底方案

If the write API is down on the day, a **飞书问卷 / 腾讯问卷** form collects votes and
takes straight into a table, with zero backend code. You can't read the response back,
but for "cast a vote," you don't need to.

如果当天写入接口挂了，用一个**飞书问卷**接收投票和观点，直接落到表格里，
完全不需要后端代码。虽然读不回来，但对"投一票"来说，够了。
