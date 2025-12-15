---
title: "Артефакт 7 — Испытания и критерии готовности (таблица)"
permalink: /artifacts/case_2/artifact_7/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_2/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_2/' | relative_url }}">К кейсу</a>
</div>

# Артефакт 7 — Испытания и критерии готовности

<p class="text-muted mb-3">
Табличная структура испытаний для кейса “Дирижёр”: проверка формирования плана, доставки заданий, маршрутов/треков, контроля выполнения (карта/Гант), перепланирования по погоде и учета поломок/задержек.
</p>

<div class="alert alert-light border mb-4">
  <div class="fw-semibold mb-1">Контекст</div>
  <div class="text-muted">
    Первые испытания на технике были проведены в <strong>3–4 квартале 2024</strong> и прошли успешно.
    Этот артефакт фиксирует “как проверяли” и “что считаем готовым” в портфолио-формате.
  </div>
</div>

## A Критерии готовности (Definition of Done)
<div class="card border shadow-sm mb-4">
  <div class="card-body">
    <div class="row g-3">
      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <div class="fw-semibold mb-2">Функциональные гейты</div>
            <ul class="mb-0">
              <li>План и сменное задание формируются, версионируются и доступны ответственным ролям.</li>
              <li>Маршруты/точки/полосы доставляются исполнителям (планшет/мобилка) и отображаются корректно.</li>
              <li>Карта и статусы техники отображают актуальную картину выполнения.</li>
              <li>Диаграмма Ганта показывает план vs факт (данные сцеплены по идентификаторам).</li>
              <li>Оповещения по погоде приходят, перепланирование выполняется и фиксируется в логах.</li>
              <li>Поломки/задержки отражаются как события и влияют на контроль/переплан (если включено правилом).</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <div class="fw-semibold mb-2">Операционные гейты</div>
            <ul class="mb-0">
              <li><strong>SLA перепланирования по погоде:</strong> ≤ 15 минут (target).</li>
              <li><strong>Качество выполнения сменного задания:</strong> 90% (target).</li>
              <li>Отсутствие критических сбоев, приводящих к потере задания/маршрута.</li>
              <li>Логи/события позволяют восстановить цепочку “план → изменение → выполнение”.</li>
            </ul>
            <div class="text-muted small mt-2">
              *Targets указаны как целевые показатели (фактическое подтверждение в эксплуатации не фиксировалось).
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

## B Сценарии испытаний (таблица)
<div class="card border shadow-sm mb-4">
  <div class="card-body">
    <div class="table-responsive">
      <table class="table align-middle mb-0">
        <thead>
          <tr>
            <th style="width:70px;">ID</th>
            <th style="min-width:220px;">Сценарий</th>
            <th style="min-width:330px;">Шаги</th>
            <th style="min-width:260px;">Ожидаемый результат</th>
            <th style="min-width:260px;">Критерии приёмки</th>
            <th style="min-width:260px;">Логи/метрики</th>
          </tr>
        </thead>
        <tbody>

          <tr>
            <td><span class="badge text-bg-light border">T1</span></td>
            <td>
              <div class="fw-semibold">Создание сменного задания</div>
              <div class="text-muted small">поле/культура/границы</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>Агроном вводит/выбирает поле, культуру.</li>
                <li>Загружает/уточняет границы поля.</li>
                <li>Сохраняет сменное задание.</li>
              </ol>
            </td>
            <td class="text-muted">
              Задание создано, валидируется и доступно ролям (агроном/диспетчер).
            </td>
            <td class="text-muted">
              Обязательные поля заполнены; геометрия поля валидна; есть версия/история изменений.
            </td>
            <td class="text-muted">
              Лог создания/изменения задания; число ошибок валидации; число правок после старта.
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">T2</span></td>
            <td>
              <div class="fw-semibold">Формирование плана и очередности уборки</div>
              <div class="text-muted small">алгоритм приоритизации</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>На основе задания запускается расчёт очередности.</li>
                <li>Техника распределяется по полям/задачам.</li>
                <li>План фиксируется и доступен для контроля.</li>
              </ol>
            </td>
            <td class="text-muted">
              План сформирован и согласован: видно “что/кто/когда”.
            </td>
            <td class="text-muted">
              Нет “пустых” задач без исполнителя; план версионирован; отображается в web.
            </td>
            <td class="text-muted">
              Время расчёта плана; число ручных корректировок; лог версий плана.
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">T3</span></td>
            <td>
              <div class="fw-semibold">Доставка задания исполнителю</div>
              <div class="text-muted small">планшет/мобилка</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>Исполнитель открывает приложение.</li>
                <li>Получает назначенное задание.</li>
                <li>Открывает маршрут/точки/полосы/тайминги.</li>
              </ol>
            </td>
            <td class="text-muted">
              Задание отображается корректно и однозначно.
            </td>
            <td class="text-muted">
              Отображается маршрут на карте; видны точки/полосы; есть очередность и тайминги.
            </td>
            <td class="text-muted">
              Время доставки/открытия задания; ошибки загрузки; журнал выдачи.
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">T4</span></td>
            <td>
              <div class="fw-semibold">Контроль выполнения (карта + статусы)</div>
              <div class="text-muted small">диспетчерский контур</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>Диспетчер открывает карту.</li>
                <li>Проверяет позиции/статусы техники.</li>
                <li>Сверяет с планом и маршрутом.</li>
              </ol>
            </td>
            <td class="text-muted">
              В web видна актуальная картина выполнения и отклонения.
            </td>
            <td class="text-muted">
              Статусы обновляются; при потере данных есть сигнал “данные устарели”.
            </td>
            <td class="text-muted">
              Лаг поступления GPS/телематики; % техники со “старыми” статусами; инциденты расхождений.
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">T5</span></td>
            <td>
              <div class="fw-semibold">Диаграмма Ганта (план vs факт)</div>
              <div class="text-muted small">визуализация задач</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>Открыть Гант по смене/полю.</li>
                <li>Сравнить плановые интервалы и фактические события.</li>
                <li>Проверить связность данных (техника/смена/поле).</li>
              </ol>
            </td>
            <td class="text-muted">
              Гант отображает корректную связку плана и факта.
            </td>
            <td class="text-muted">
              Нет “висящих” задач без факта (если факт есть); события привязаны к технике/смене.
            </td>
            <td class="text-muted">
              % задач с фактом; % событий без привязки; время загрузки Ганта.
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">T6</span></td>
            <td>
              <div class="fw-semibold">Оптимизация логистики БП</div>
              <div class="text-muted small">комбайн ↔ БП ↔ зерновоз</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>Запустить сценарий расчёта маршрутов/таймингов БП.</li>
                <li>Проверить учёт “доезд → выгрузка → переезд”.</li>
                <li>Проверить расчёт “сколько комбайнов обслужит БП”.</li>
              </ol>
            </td>
            <td class="text-muted">
              План логистики согласован с ограничениями, минимизирует ожидания комбайнов.
            </td>
            <td class="text-muted">
              Алгоритм не приводит к ситуации “комбайн остановился из-за логистики” в тестовых сценариях.
            </td>
            <td class="text-muted">
              Простои/ожидания в сценариях; сравнение с baseline; лог решений алгоритма.
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">T7</span></td>
            <td>
              <div class="fw-semibold">Оповещение о погоде</div>
              <div class="text-muted small">уведомления</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>Сымитировать/дождаться погодного события.</li>
                <li>Проверить доставку уведомлений в web/мобильное.</li>
                <li>Проверить журнал оповещений.</li>
              </ol>
            </td>
            <td class="text-muted">
              Уведомления приходят вовремя, соответствуют правилам.
            </td>
            <td class="text-muted">
              Нет “шума” (ложных тревог); есть фиксированная причина/порог срабатывания.
            </td>
            <td class="text-muted">
              Время доставки уведомления; число ложных срабатываний; лог порогов.
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">T8</span></td>
            <td>
              <div class="fw-semibold">Перепланирование по погоде</div>
              <div class="text-muted small">пересчёт графика</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>Инициировать переплан (по погоде).</li>
                <li>Пересчитать график работ.</li>
                <li>Опубликовать новую версию плана и доставить изменения.</li>
              </ol>
            </td>
            <td class="text-muted">
              План пересчитан и доведён до пользователей, изменения видны диспетчеру.
            </td>
            <td class="text-muted">
              SLA перепланирования ≤ 15 минут (target); лог версий; возможность отката.
            </td>
            <td class="text-muted">
              Время переплана; число версий/откатов; уведомления о смене плана.
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">T9</span></td>
            <td>
              <div class="fw-semibold">Поломка техники / логистическая задержка</div>
              <div class="text-muted small">инциденты</div>
            </td>
            <td>
              <ol class="mb-0">
                <li>Сымитировать событие “поломка” или “задержка”.</li>
                <li>Проверить появление в системе (карта/Гант/уведомления).</li>
                <li>Проверить влияние на контроль/переплан (если предусмотрено правилом).</li>
              </ol>
            </td>
            <td class="text-muted">
              Событие фиксируется и используется в управлении кампанией.
            </td>
            <td class="text-muted">
              Инцидент имеет причину/классификацию; виден диспетчеру; не теряется.
            </td>
            <td class="text-muted">
              % инцидентов с заполненной причиной; время реакции; статистика простоев по причинам.
            </td>
          </tr>

        </tbody>
      </table>
    </div>
  </div>
</div>

## C Ссылки на связанные артефакты
<div class="row g-3">
  <div class="col-12 col-lg-4">
    <a class="card h-100 shadow-sm text-decoration-none" href="{{ '/artifacts/case_2/artifact_1/' | relative_url }}">
      <div class="card-body">
        <div class="fw-semibold">Артефакт 1</div>
        <div class="text-muted">North Star и KPI-дерево</div>
      </div>
    </a>
  </div>
  <div class="col-12 col-lg-4">
    <a class="card h-100 shadow-sm text-decoration-none" href="{{ '/artifacts/case_2/artifact_4/' | relative_url }}">
      <div class="card-body">
        <div class="fw-semibold">Артефакт 4</div>
        <div class="text-muted">Карта зависимостей (таблица)</div>
      </div>
    </a>
  </div>
  <div class="col-12 col-lg-4">
    <a class="card h-100 shadow-sm text-decoration-none" href="{{ '/artifacts/case_2/artifact_5/' | relative_url }}">
      <div class="card-body">
        <div class="fw-semibold">Артефакт 5</div>
        <div class="text-muted">Top-риски и меры (таблица)</div>
      </div>
    </a>
  </div>
</div>
