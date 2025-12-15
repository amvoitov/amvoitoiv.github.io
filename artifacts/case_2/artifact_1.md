---
title: "Артефакт 1 — North Star и KPI-дерево"
permalink: /artifacts/case_2/artifact_1/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_2/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_2/' | relative_url }}">К кейсу</a>
</div>

# North Star и KPI-дерево

<div class="alert alert-light border">
  <strong>Важно:</strong> ниже — целевая модель метрик (targets) для проекта. Подтверждённые фактические значения в эксплуатации не зафиксированы.
</div>

## North Star Metric (NSM)
<div class="card shadow-sm">
  <div class="card-body">
    <div class="fw-semibold mb-1">“Объём уборки, выполненный по плану”</div>
    <div class="text-muted">
      Убранная площадь/вес (га/тонн), подтверждённые телематикой, выполненные в рамках сменного задания за период.
    </div>
  </div>
</div>

## KPI-дерево (драйверы)
<div class="row g-3 mt-1">
  <div class="col-12 col-lg-6">
    <div class="card h-100 shadow-sm">
      <div class="card-body">
        <div class="fw-semibold mb-2">Эффективность логистики</div>
        <ul class="mb-0">
          <li><strong>Простои техники:</strong> target −40%</li>
          <li><strong>Холостые пробеги:</strong> target −30%</li>
          <li><strong>Время уборки поля:</strong> target −20%</li>
        </ul>
      </div>
    </div>
  </div>

  <div class="col-12 col-lg-6">
    <div class="card h-100 shadow-sm">
      <div class="card-body">
        <div class="fw-semibold mb-2">Адаптивность к погоде</div>
        <ul class="mb-0">
          <li><strong>Время перепланирования:</strong> ≤ 15 минут</li>
          <li><strong>Доля выполненных перепланирований без срыва смены:</strong> (метрика уточняется)</li>
        </ul>
      </div>
    </div>
  </div>

  <div class="col-12 col-lg-6">
    <div class="card h-100 shadow-sm">
      <div class="card-body">
        <div class="fw-semibold mb-2">Качество исполнения задания</div>
        <ul class="mb-0">
          <li><strong>Качество/точность выполнения сменного задания:</strong> 90%</li>
          <li><strong>Отклонения от маршрута/таймингов:</strong> (метрика уточняется)</li>
        </ul>
      </div>
    </div>
  </div>

  <div class="col-12 col-lg-6">
    <div class="card h-100 shadow-sm">
      <div class="card-body">
        <div class="fw-semibold mb-2">Производительность</div>
        <ul class="mb-0">
          <li><strong>Производительность:</strong> т/час, га/смена (target: рост относительно базовой кампании)</li>
          <li><strong>Загрузка парка:</strong> (метрика уточняется)</li>
        </ul>
      </div>
    </div>
  </div>
</div>
