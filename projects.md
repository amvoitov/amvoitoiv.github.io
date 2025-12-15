---
title: "Кейсы"
permalink: /projects/
---

<div class="card shadow-sm rounded-4 p-4 p-lg-5 page-card">
  <h1 class="display-6 fw-bold mb-2">Проекты</h1>
  <p class="text-muted mb-4">
    Ниже — кейсы. В каждом: контекст, требования, моя роль, ключевые действия, результат и артефакты.
  </p>

  {% assign cases = site.pages
    | where_exp: "p", "p.url contains '/projects/case_'"
    | sort: "url" %}

  <div class="row g-4 row-cols-1 row-cols-xl-2">
    {% for c in cases %}
      <div class="col">
        <div class="card h-100 shadow-sm rounded-4">
          <div class="card-body d-flex flex-column gap-3">
            <div class="d-flex align-items-start justify-content-between gap-3">
              <div>
                <div class="h5 fw-bold mb-1">{{ c.case_title_short | default: c.title }}</div>

                {% if c.case_tags %}
                  <div class="d-flex flex-wrap gap-2">
                    {% for t in c.case_tags %}
                      <span class="badge text-bg-light border">{{ t }}</span>
                    {% endfor %}
                  </div>
                {% endif %}
              </div>
            </div>

            {% if c.case_short %}
              <p class="text-muted mb-0">{{ c.case_short }}</p>
            {% else %}
              <p class="text-muted mb-0">Описание добавим после твоих ответов (без придуманных деталей).</p>
            {% endif %}

            <!-- метрики: 2 колонки на узких, 4 на md+ -->
            <div class="row g-2 row-cols-2 row-cols-md-4 mt-1">
              <div class="col">
                <div class="metric-card h-100">
                  <div class="metric-label">Роль</div>
                  <div class="metric-value">{{ c.case_role | default: '—' | replace: '/', ' / ' }}</div>
                </div>
              </div>
              <div class="col">
                <div class="metric-card h-100">
                  <div class="metric-label">Период</div>
                  <div class="metric-value">{{ c.case_period | default: '—' }}</div>
                </div>
              </div>
              <div class="col">
                <div class="metric-card h-100">
                  <div class="metric-label">Команда</div>
                  <div class="metric-value">{{ c.case_team | default: '—' }}</div>
                </div>
              </div>
              <div class="col">
                <div class="metric-card h-100">
                  <div class="metric-label">Эффект</div>
                  <div class="metric-value">{{ c.case_effect | default: '—' }}</div>
                </div>
              </div>
            </div>

            <div class="mt-auto d-flex flex-wrap gap-2">
              <a class="btn btn-primary" href="{{ c.url | relative_url }}">Открыть кейс</a>
              {% if c.case_artifacts_url %}
                <a class="btn btn-outline-secondary" href="{{ c.case_artifacts_url | relative_url }}">Артефакты</a>
              {% endif %}
            </div>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>
</div>
