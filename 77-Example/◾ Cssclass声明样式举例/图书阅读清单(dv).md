---
cssclass: "cards"
usage: "对dataview表格渲染成卡片视图"
banner: "99-Attachment/banner/book.jpg"
obsidianUIMode: "preview"
updated: "2022-03-10 23:59"
---

> 实现方法参考[[如何在Obsidian中添加图书卡片]]


```dataview
table without id ("![](" + cover + ")") as Cover,  "<progress value=" + pageprogress + " max="+pagecount+"  class='yellow'>" as progress,file.link as Name, author as Author,publish,rating as Rating
from #book 
where !contains(file.folder, "88-Template") 
sort rating desc

```



