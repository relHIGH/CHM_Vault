---
title: 关系图谱
layout: default
---

<div id="graph-container" style="width: 100%; height: 70vh; background: #fdfaf6; border-radius: 12px; border: 1px solid #eee; position: relative; overflow: hidden;">
  <div id="graph-loading" style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); color: #999;">正在构建神经网络...</div>
</div>

<script src="https://unpkg.com/force-graph"></script>
<script>
  window.addEventListener("DOMContentLoaded", () => {
    fetch("{{ site.baseurl }}/assets/graph_data.json")
      .then(res => res.json())
      .then(data => {
        document.getElementById("graph-loading").style.display = "none";
        const elem = document.getElementById("graph-container");
        const Graph = ForceGraph()(elem)
          .graphData(data)
          .nodeId("id")
          .nodeLabel("id")
          .nodeColor(() => "#e67e22")
          .linkColor(() => "#ddd")
          .linkDirectionalParticles(2)
          .linkDirectionalParticleSpeed(d => 0.01)
          .onNodeClick(node => {
            // 点击节点跳转
            const found = pages.find(p => p.name === node.id);
            if (found) window.location.href = found.url;
          });
        
        // 自动适配容器大小
        window.addEventListener("resize", () => {
          Graph.width(elem.offsetWidth).height(elem.offsetHeight);
        });
      });
  });
</script>

---
> 💡 **提示**：你可以通过鼠标滚轮缩放，左键点击节点可以跳转到对应笔记。
