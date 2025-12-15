---
title: "Артефакт 5 — Top-риски и меры"
permalink: /artifacts/case_2/artifact_5/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_2/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_2/' | relative_url }}">К кейсу</a>
</div>

# Top-риски и меры

<div class="card shadow-sm">
  <div class="card-body">
    <ul class="mb-0">
      <li><strong>Низкое качество GPS/границ поля</strong> → неверные маршруты → валидация геометрии поля + контроль качества треков.</li>
      <li><strong>Неполные телематические события</strong> → “слепая” оптимизация → минимальный обязательный набор параметров + мониторинг пропусков.</li>
      <li><strong>Погодные изменения</strong> → срыв сменного задания → правила перепланирования + SLA на пересчёт (≤15 мин).</li>
      <li><strong>Ошибки алгоритмов оптимизации</strong> → рост простоев → тест-кейсы на сценарии + сравнение с базовым планом.</li>
      <li><strong>Низкое принятие механизаторами</strong> → задания игнорируются → простой интерфейс: маршрут/точки/тайминги + обучение.</li>
      <li><strong>Интеграции/данные недоступны</strong> → деградация функций → fallback на ручной ввод (сменное задание/статусы).</li>
    </ul>
  </div>
</div>
