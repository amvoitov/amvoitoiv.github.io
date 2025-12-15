---
title: "Артефакт 5 — Карта зависимостей"
permalink: /artifacts/case_1/artifact_5/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_1/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_1/' | relative_url }}">К кейсу</a>
</div>

<div class="card shadow-sm">
  <div class="card-body p-4">

    <div class="d-flex flex-wrap align-items-center justify-content-between gap-2 mb-2">
      <h1 class="h3 mb-0">Карта зависимостей</h1>
      <span class="badge text-bg-light border">ТЗ Web-Automation</span>
    </div>

    <p class="text-secondary mb-4">
      Что от чего зависит в системе: привязка БП, качество данных, отчётность, Employee App и “Свой-Чужой”.
    </p>

    <h2 class="h5 mb-3">Схема зависимостей</h2>

    <div class="card border mb-4">
      <div class="card-body">
        <div class="ratio ratio-21x9">
          <svg viewBox="0 0 1200 520" width="100%" height="100%" role="img" aria-label="Схема зависимостей компонентов">
            <defs>
              <style>
                .b { fill: #ffffff; stroke: #cfd6df; stroke-width: 2; }
                .t { font: 18px system-ui, -apple-system, Segoe UI, Roboto, Arial; fill: #0f172a; }
                .s { font: 14px system-ui, -apple-system, Segoe UI, Roboto, Arial; fill: #475569; }
                .a { stroke: #94a3b8; stroke-width: 3; fill: none; marker-end: url(#arrow); }
              </style>
              <marker id="arrow" markerWidth="12" markerHeight="12" refX="10" refY="6" orient="auto">
                <path d="M0,0 L12,6 L0,12 z" fill="#94a3b8"></path>
              </marker>
            </defs>

            <!-- Nodes -->
            <rect class="b" x="60"  y="70"  rx="14" ry="14" width="360" height="130"></rect>
            <text class="t" x="80" y="108">Web: “Привязка БП”</text>
            <text class="s" x="80" y="138">имя БВС + код</text>
            <text class="s" x="80" y="162">оффлайн-сценарий</text>
            <text class="s" x="80" y="186">история регистраций</text>

            <rect class="b" x="60"  y="250" rx="14" ry="14" width="360" height="120"></rect>
            <text class="t" x="80" y="288">Android: “Зарегистрировать/код”</text>
            <text class="s" x="80" y="318">генерация/показ/отправка кода</text>
            <text class="s" x="80" y="342">поддержка offline</text>

            <rect class="b" x="470" y="90"  rx="14" ry="14" width="300" height="120"></rect>
            <text class="t" x="490" y="128">Справочники</text>
            <text class="s" x="490" y="158">поля / техника / сотрудники</text>
            <text class="s" x="490" y="182">активность админа</text>

            <rect class="b" x="470" y="250" rx="14" ry="14" width="300" height="160"></rect>
            <text class="t" x="490" y="288">Качество данных операций</text>
            <text class="s" x="490" y="318">тип / дата / время</text>
            <text class="s" x="490" y="342">GPS / идентификация</text>
            <text class="s" x="490" y="366">чеки / корректные связи</text>

            <rect class="b" x="820" y="90"  rx="14" ry="14" width="320" height="120"></rect>
            <text class="t" x="840" y="128">Отчёты / рейтинг / статистика</text>
            <text class="s" x="840" y="158">зависят от справочников</text>
            <text class="s" x="840" y="182">и качества операций</text>

            <rect class="b" x="820" y="250" rx="14" ry="14" width="320" height="120"></rect>
            <text class="t" x="840" y="288">Employee App</text>
            <text class="s" x="840" y="318">учётки сотрудников</text>
            <text class="s" x="840" y="342">API чеков/календаря</text>

            <rect class="b" x="820" y="400" rx="14" ry="14" width="320" height="90"></rect>
            <text class="t" x="840" y="438">“Свой-Чужой”</text>
            <text class="s" x="840" y="468">RFID + реле блокировки</text>

            <rect class="b" x="470" y="420" rx="14" ry="14" width="300" height="70"></rect>
            <text class="t" x="490" y="455">Hardware/правила</text>
            <text class="s" x="490" y="478">антенны/реле + “ближайшее ТС”</text>

            <!-- Arrows -->
            <path class="a" d="M420,135 C450,135 450,300 420,310"></path>
            <path class="a" d="M420,310 C450,310 450,135 470,150"></path>

            <path class="a" d="M770,150 C800,150 805,150 820,150"></path>
            <path class="a" d="M770,330 C800,330 805,170 820,170"></path>

            <path class="a" d="M420,310 C450,310 460,310 470,320"></path>

            <path class="a" d="M470,150 C520,150 520,320 470,320"></path>

            <path class="a" d="M770,455 C800,455 805,455 820,445"></path>
          </svg>
        </div>
      </div>
    </div>

    <h2 class="h5 mb-3">Зависимости (текстом)</h2>

    <div class="row g-3">
      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <h3 class="h6">Привязка БП: Web ⇄ Android</h3>
            <ul class="mb-0">
              <li><b>Web “Привязка БП” ⇄ Android “Зарегистрировать/код”</b></li>
              <li>Имя БВС + код</li>
              <li>Оффлайн-сценарий</li>
              <li>История регистраций</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <h3 class="h6">Отчёты / рейтинг / статистика</h3>
            <ul class="mb-0">
              <li>Зависят от <b>заполненных справочников</b> (поля/техника/сотрудники)</li>
              <li>И от <b>корректных данных операций</b> (тип/дата/время/GPS/идентификация)</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <h3 class="h6">Employee App</h3>
            <ul class="mb-0">
              <li>Зависит от наличия <b>учёток сотрудников</b> (логин/пароль)</li>
              <li>И от <b>API выдачи чеков/календаря</b></li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <h3 class="h6">“Свой-Чужой”</h3>
            <ul class="mb-0">
              <li>Зависит от монтажа <b>RFID-антенн</b> и <b>реле блокировки шнека</b></li>
              <li>И от правил: <b>“ближайшее ТС” / ручной режим</b></li>
            </ul>
          </div>
        </div>
      </div>
    </div>

  </div>
</div>
