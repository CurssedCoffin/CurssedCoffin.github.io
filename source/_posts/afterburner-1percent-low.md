---
title: MSI Afterburner 1% Low 帧不显示或显示值异常（1FPS）
tags: [MSI Afterburner, Rivatuner, OSD, 帧率显示, FPS]
categories: [故障解决]
mathjax: false
date: 2025-06-08 00:55:30
---

# 解决
- 若要在  **Afterburner** 中使用统计信息（Min，Max，Avg），则需要在 **Rivatuner** 中的设置中启用 **benchmark mode**，所选的功能才可以在 **Afterburner** 中显示

- 如果统计信息显示不准（比如1%Low帧显示1FPS），则需要将 **Rivatuner** 的 **Percentile buffer** 设置从默认的 **default** 更改到 **ring**
<!-- more -->
{%asset_img Rivatuner.png%}
