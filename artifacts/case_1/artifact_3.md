---
title: "Артефакт 3 — Story Map (MVP → v1 → v2)"
permalink: /artifacts/case_1/artifact_3/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_1/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_1/' | relative_url }}">К кейсу</a>
</div>

<div class="card shadow-sm">
  <div class="card-body p-4">

    <h1 class="h3 mb-2">Story Map (MVP → v1 → v2)</h1>
    <p class="text-secondary mb-4">
      Разбиение пользовательских активностей и инкрементов: MVP, v1, v2.
    </p>

    <div class="row g-3">

      <!-- Активность A -->
      <div class="col-12">
        <div class="card border">
          <div class="card-body">
            <div class="d-flex flex-wrap align-items-center justify-content-between gap-2 mb-2">
              <h2 class="h5 mb-0">Активность A: “Зафиксировать операцию на БП”</h2>
              <span class="badge text-bg-light border">MVP → v1 → v2</span>
            </div>

            <ul class="mb-3">
              <li><b>A1</b> Отобразить вес / выбрать режим</li>
              <li><b>A2</b> Идентифицировать технику (RFID/ручной выбор)</li>
              <li><b>A3</b> Сохранить транзакцию + чек</li>
              <li><b>A4</b> Отправить на сервер / положить в offline-очередь</li>
            </ul>

            <div class="d-flex flex-wrap gap-2">
              <span class="badge text-bg-primary">MVP: A1–A4</span>
              <span class="badge text-bg-secondary">v1: “Свой/чужой” (RFID + блокировка/разблокировка)</span>
              <span class="badge text-bg-light border">v2: расширенные сценарии ошибок/инженерка/оборудование</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Активность B -->
      <div class="col-12">
        <div class="card border">
          <div class="card-body">
            <div class="d-flex flex-wrap align-items-center justify-content-between gap-2 mb-2">
              <h2 class="h5 mb-0">Активность B: “Подключить БП к хозяйству”</h2>
              <span class="badge text-bg-light border">MVP</span>
            </div>

            <ul class="mb-3">
              <li><b>B1</b> На сайте: ввести имя БВС + код, привязать БП к аккаунту</li>
              <li><b>B2</b> На планшете: “Зарегистрировать” и показать/отправить код</li>
              <li><b>B3</b> История регистраций и защита от повторных/чужих привязок</li>
            </ul>

            <div class="d-flex flex-wrap gap-2">
              <span class="badge text-bg-primary">MVP: B1–B3</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Активность C -->
      <div class="col-12">
        <div class="card border">
          <div class="card-body">
            <div class="d-flex flex-wrap align-items-center justify-content-between gap-2 mb-2">
              <h2 class="h5 mb-0">Активность C: “Управлять хозяйством и контролировать уборку”</h2>
              <span class="badge text-bg-light border">MVP → v1 → v2</span>
            </div>

            <ul class="mb-3">
              <li><b>C1</b> Главная: календарь + карта + список БП и транзакций</li>
              <li><b>C2</b> Справочники: поля/техника/сотрудники</li>
              <li><b>C3</b> Рейтинг сотрудников</li>
              <li><b>C4</b> Статистика/отчёты (техника/сотрудники/поля)</li>
              <li><b>C5</b> “Сообщить о проблеме”</li>
            </ul>

            <div class="d-flex flex-wrap gap-2">
              <span class="badge text-bg-primary">MVP: C1–C2</span>
              <span class="badge text-bg-secondary">v1: C3–C4</span>
              <span class="badge text-bg-light border">v2: C5 + расширения (публикация рейтинга/соцсети)</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Активность D -->
      <div class="col-12">
        <div class="card border">
          <div class="card-body">
            <div class="d-flex flex-wrap align-items-center justify-content-between gap-2 mb-2">
              <h2 class="h5 mb-0">Активность D: “Сотруднику — электронный чек”</h2>
              <span class="badge text-bg-light border">MVP</span>
            </div>

            <ul class="mb-3">
              <li><b>D1</b> Вход: организация + логин/пароль</li>
              <li><b>D2</b> Подтверждение: 6-значный код, подключение через ответственного</li>
              <li><b>D3</b> Календарь с подсветкой дат работ + просмотр поля/чека</li>
            </ul>

            <div class="d-flex flex-wrap gap-2">
              <span class="badge text-bg-primary">MVP: D1–D3 (онлайн-режим)</span>
            </div>
          </div>
        </div>
      </div>

    </div><!-- /row -->
  </div>
</div>
