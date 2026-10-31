---
name: medxpert-deficiency-reply-skill
description: 医疗器械注册发补回复撰写指导。输入FDA/NMPA/公告机构的发补信，输出回复框架+逐条应答要点+补充材料清单。Use for：510(k)发补回复、CE-MDR发补回复、NMPA发补回复、RTA拒收后的应对。Do NOT use for：注册路径选择（用medxpert-reg-path-skill）、申报前自查（用medxpert-pre-submission-check-skill）。触发词：发补回复、补正回复、deficiency letter、AI letter、RTA、审评意见回复。
---

# MedXpert Deficiency Reply Skill · 发补回复撰写指导

> 这是MedXpert Skill全家桶的第三环：
> ① 路径决策 → ② 申报前自查 → ③ **发补回复** → ④ 临床评价
> 提交之后收到发补信，别慌——这个Skill帮你逐条拆解、组织回复。

## 这个 Skill 做什么

收到审评机构的发补信（AI Letter / Deficiency Letter / 发补通知），最头疼的是：
1. 不知道每条意见到底在问什么
2. 不知道怎么答才专业，答不好又要再发一轮
3. 不知道要补哪些材料，漏了又要等几个月

这个Skill帮你：
- 逐条拆解发补意见，翻译成大白话
- 给出每条的回复框架和要点
- 列出需要补充的材料清单
- 提醒回复时限和注意事项

**它不是帮你代写全文，是帮你搭回复框架、不踩坑。**

---

## 何时使用

### ✅ 合适的场景

- 刚收到FDA/NMPA/公告机构的发补信，不知道怎么下手
- 写发补回复之前，先理清楚每条意见的应对思路
- 审核别人写的发补回复，看看有没有答偏

### ❌ 不合适的场景

- 注册路径还没定（先用①路径决策）
- 还没提交，先做自查（用②申报前自查）
- 临床实验方案设计（用④临床评价）

---

## 工作流

### Step 1 · 先确认基本信息

先问清楚：
- 哪个市场的发补？（美国FDA / 欧盟MDR / 中国NMPA）
- 产品是什么？之前走的什么路径？
- 发补时限还有多久？（FDA一般180天，中国1年）

### Step 2 · 逐条拆解发补意见

把发补信里的每条意见拆出来，逐条分析：
- 这条意见到底在问什么？
- 审评员为什么问这个？（是材料没写清楚，还是数据不够？）
- 应该怎么答？需要补什么材料？

### Step 3 · 输出回复框架

输出格式：
```
发补意见第X条：[原文]
审评员想问的其实是：[大白话翻译]
回复要点：
1. ...
2. ...
需要补充的材料：
- ...
风险提示：[这条如果答不好，可能会再发一轮]
```

### Step 4 · 提醒注意事项

- 回复时限：别超期，超期视为撤回
- 回复格式：按审评机构要求的格式来
- 逐条对应：一条意见对应一段回复，不要混在一起

---

## 硬规则

### 🚫 P0级禁令

1. **不许跳过任何一条发补意见**——有多少条就拆多少条
2. **不许说"这个意见不重要"**——审评员提出来的都重要
3. **每条回复必须有要点和材料清单**——不能只说"我们会补充"
4. **不许编造数据**——需要补数据就说"待补充"，不能瞎编

---

## 资源文件导览

```
medxpert-deficiency-reply-skill/
├── SKILL.md
├── references/
│   ├── us-510k-deficiency-types.md   ← FDA 510(k)常见发补类型和应对
│   ├── eu-mdr-deficiency-types.md    ← 欧盟MDR常见发补类型
│   └── cn-nmpa-deficiency-types.md   ← 中国NMPA常见发补类型
└── assets/
    └── cases/
        ├── README.md                 ← 案例库索引与案例结构说明
        └── US-001-orthopedic-external-fixator-recall.md
                                       ← 真实发补案例：Predicate被认定不成立
```

---

> 🛡️ 本Skill是MedXpert LGD体系的一环：有籍有证有门禁。
> 更多Skill：[①路径决策](../medxpert-reg-path-skill/) · [②申报前自查](../medxpert-pre-submission-check-skill/)
