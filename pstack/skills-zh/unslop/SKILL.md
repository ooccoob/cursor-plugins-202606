---
name: unslop
description: 从任何文字中剪除 AI 痕迹。
disable-model-invocation: true
---

# 去水化（Unslop）

编辑文本以去除 AI 模式。扫描下面的模式，然后重写。保留原意，匹配预期语气。

规则编号是稳定的 id，其他技能会引用它们。删掉一条规则会留下空号。

3. 不要用不携带任何事实的句尾 "-ing" 短语（"highlighting..."、"ensuring..."）。
5. 不要含糊的归属（"experts believe"）。点名来源，或删掉它。
7. 不用 AI 词汇：additionally、crucial、delve、enhance、foster、landscape、pivotal、showcase、testament、underscore、vibrant。
8. 说 "is" 或 "has"，不用 "serves as"、"stands as"、"boasts"、"features"。
9. 不用 "not just X, but Y"。直接陈述要点。
10. 不要把想法硬凑成三条。
11. 一样东西一个名字。重复使用它。
12. 不用 "from X to Y"，除非 X 和 Y 处在真实的刻度上。
13. 不用 em dash、en dash，或把连字符当破折号用，也不要用括号替代它们。用句号或逗号。
14. 冒号放在列表或示例之前，绝不在句子中间当连接词。
15. 不要给每个专有名词或缩写加粗。
16. 不要用加粗标签加冒号来重复它所在的那一行（"**Performance:** Performance improved..."）。以句号结尾并添加新细节的加粗引导语是可以的。
17. 标题用句首大写。
18. 不用装饰性 emoji。
19. 用直引号。
20. 不用聊天机器人式短语（"I hope this helps!"、"Let me know if..."）。
22. 不用赞美或附和式开头。直接回应。
23. 删掉填充语。"In order to" 改成 "to"。删掉 "it is important to note that"。
24. 最多一个模糊限定词："may"。
25. 不用泛泛的结论。陈述具体的计划或事实。
26. 不用抽象隐喻名词：substrate、wedge、vector、nexus、primitive、harness、surface、scaffolding、paradigm、ratchet、north star、flywheel。用具体的词。
27. 说它做什么，不说它感觉如何。点名机制或数字。删掉那种原样放进另一个项目文档里也成立的句子。
28. 一句一个想法。拆开读者需要重读的句子。
29. 用主动语态。点名施动者，除非它未知或不重要。
30. 删掉副词，或换一个更强的动词。给出数字。
31. 用朴素的词："use"，而不是 "utilize" 或 "leverage"。
32. 不用隐喻、格言、拟人化的代码，或在有字面表达时用比喻性动词。
33. 写完整的句子，带上冠词和动词。把箭头和缩写展开写。
