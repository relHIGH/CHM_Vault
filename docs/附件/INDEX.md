
> [!summary] 题型累计
> ```dataviewjs
> const files = app.vault.getMarkdownFiles();
> 
> // 排除文件夹（可选）
> const excludeFolders = ["附件", "INDEX","a0-真题库"];
> const filteredFiles = files.filter(file => 
>     !excludeFolders.some(folder => file.path.includes(folder + "/"))
> );
> 
> let a = 0, b = 0, c = 0;
> 
> for (let file of filteredFiles) {
>     const content = await app.vault.cachedRead(file);
>     
>     // 关键改动：用 match(/.../g) 统计所有出现次数，而不是 contains()
>     const tips = content.match(/> \[!tip\]/g);
>     const examples = content.match(/> \[!example\]/g);
>     const notes = content.match(/> \[!note\]/g);
>     
>     if (tips) a += tips.length;           // 累加个数
>     if (examples) b += examples.length;   // 累加个数
>     if (notes) c += notes.length;         // 累加个数
> }
> 
> dv.paragraph(`- **名词解释**：${a} 个`);
> dv.paragraph(`- **简答**：${b} 个`);
> dv.paragraph(`- **论述**：${c} 个`);
> dv.paragraph(`<small>专题：${filteredFiles.length} | 总题数：${a+b+c}</small>`);
> ```

### 待补充
- [ ]  [[保护工程管理#中华文明探源工程]]
- [ ] [[边疆考古]]
- [ ] [[遗址#辽金元城址]]
- [ ] [[五年内重大项目]]
- [ ] [[NJU-N5]]







### 题型确定情况

- [ ] 名词: 1 简答:1  论述:      [[博物馆学]]
- [ ] 名词: 3 简答:  论述: 1     [[考古学范式]]
- [ ] 名词: 3 简答: 1 论述:      [[史前理论范式]]
- [ ] 名词: 2 简答:  论述: 2     [[文物学]]
- [ ] 名词:  简答:  论述: 4     [[学科发展史]]

- [ ] 名词:  简答:  论述: 3     [[鉴定方法论]]
- [ ] 名词:  简答:  论述:      [[古建筑古遗址]]
- [ ] 名词:  简答:  论述:      [[古墓葬]]
- [ ] 名词: 1 简答: 1 论述:      [[古钱币]]
- [ ] 名词: 1 简答: 2 论述:  2    [[BOX/A-题/a2-工艺、病害与修复/书画古籍]]
- [ ] 名词: 1 简答:  论述:2      [[⚱️冶金考古]]
- [ ] 名词:  简答: 1 论述:      [[漆木竹骨角牙]]
- [ ] 名词:  简答:  论述:      [[石窟-壁画彩塑]]
- [ ] 名词:  简答:  论述:      [[陶瓷科技考古]]
- [ ] 名词:  1 简答:  论述:  2    [[石质文物]]
- [ ] 名词:  简答:  论述: 1   [[🫟玺印]]

- [ ] 名词:  简答: 1 论述: 1     [[保护工程管理]]
- [ ] 名词: 1 简答:  论述: 1     [[藏品保护]]
- [ ] 名词: 2 简答:1  论述:      [[法律法规]]
- [ ] 名词: 1 简答:  论述: 1     [[线性遗产]]
- [ ] 名词: 1 简答:  论述:  1    [[遗址管理]]
- [ ] 名词: 1 简答: 1 论述:      [[田野考古]]

- [ ] 名词:  简答: 2 论述:      [[成分结构形态分析]]
- [ ] 名词: 1 简答: 1 论述:  2    [[断代与溯源技术]]
- [ ] 名词: 6 简答: 1 论述: 1     [[科技考古类型]]

- [ ] 名词: 1 简答:  论述: 1   [[教育与观众研究]]
- [ ] 名词:  简答: 1 论述: 2     [[经营与策略]]
- [ ] 名词: 1 简答: 1 论述:2      [[展览策划]]
- [ ] 名词: 1 简答:1  论述: 1  [[数字博物馆]]


