---
layout: default
title: 洪清档案
---
<div class="filters" id="filters">
  <div class="group">
    <label>🔎 搜索</label>
    <input id="q" type="text" placeholder="按标题关键字过滤…" />
  </div>
  <div class="group">
    <label>📅 年份</label>
    <select id="year">
      <option value="">全部年份</option>
      <!-- 年份选项会在脚本中自动填充 -->
    </select>
  </div>
  <small>提示：三栏同时过滤，仅匹配“时间 + 标题”。</small>
</div>

<div class="triple-grid">

  <!-- 真实史料（红） -->
  <section class="column history" id="history">
    <div class="col-head">
      <div class="bar"></div><h2>真实史料</h2>
    </div>
    <ul class="mini-list">
      {%- assign history_items = site.history | where: "verification_status","approved" | sort: "date_event" -%}
      {%- for doc in history_items -%}
      <li class="mini-row">
        <span class="date">{{ doc.date_event }}</span>
        <a href="{{ doc.url | relative_url }}">{{ doc.title }}</a>
      </li>
      {%- endfor -%}
    </ul>
  </section>

  <!-- 娱乐信息（蓝） -->
  <section class="column ent" id="entertainment">
    <div class="col-head">
      <div class="bar"></div><h2>娱乐信息</h2>
    </div>
    <ul class="mini-list">
      {%- assign ent_items = site.entertainment | where: "verification_status","approved" | sort: "date_event" -%}
      {%- for doc in ent_items -%}
      <li class="mini-row">
        <span class="date">{{ doc.date_event }}</span>
        <a href="{{ doc.url | relative_url }}">{{ doc.title }}</a>
      </li>
      {%- endfor -%}
    </ul>
  </section>

  <!-- 玄学信息（绿） -->
  <section class="column meta" id="metaphysics">
    <div class="col-head">
      <div class="bar"></div><h2>玄学信息</h2>
    </div>
    <ul class="mini-list">
      {%- assign meta_items = site.metaphysics | where: "verification_status","approved" | sort: "date_event" -%}
      {%- for doc in meta_items -%}
      <li class="mini-row">
        <span class="date">{{ doc.date_event }}</span>
        <a href="{{ doc.url | relative_url }}">{{ doc.title }}</a>
      </li>
      {%- endfor -%}
    </ul>
  </section>

</div>
