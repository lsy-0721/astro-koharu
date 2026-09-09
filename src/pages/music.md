---
layout: ../layouts/PageLayout.astro
title: "歌单"
description: "我喜欢的音乐"
---

这里可以放你喜欢的音乐歌单。

使用 `{% media audio %}` 标签嵌入网易云音乐或 QQ 音乐歌单：

```markdown
{% media audio %}
- title: 我的歌单
  list:
    - https://music.163.com/#/playlist?id=你的歌单ID
{% endmedia %}
```

{% media audio %}
- title: miHoYo
  list:
    - https://music.163.com/#/my/m/music/playlist?id=18366625500
- title: soft
  list:
    - https://music.163.com/#/playlist?id=18068725100
{% endmedia %}
