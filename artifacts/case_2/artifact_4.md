---
title: "Артефакт 4 — Карта зависимостей (таблица)"
permalink: /artifacts/case_2/artifact_4/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_2/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_2/' | relative_url }}">К кейсу</a>
</div>

# Артефакт 4 — Карта зависимостей

<p class="text-muted mb-3">
Табличная карта “что от чего зависит” для планирования, маршрутов, контроля выполнения (карта/Гант), перепланирования по погоде и анализа простоев/поломок.
</p>

<div class="card border shadow-sm mb-4">
  <div class="card-body">
    <div class="row g-3">
      <div class="col-12 col-lg-4">
        <div class="card border h-100">
          <div class="card-body">
            <div class="fw-semibold mb-1">Зачем это в портфолио</div>
            <div class="text-muted">Показывает системное мышление: где “узкие места” и что контролировать метриками.</div>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-4">
        <div class="card border h-100">
          <div class="card-body">
            <div class="fw-semibold mb-1">Где ломается чаще всего</div>
            <div class="text-muted">Данные: границы поля, GPS, телематика (статусы/поломки), ручной ввод сменного задания.</div>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-4">
        <div class="card border h-100">
          <div class="card-body">
            <div class="fw-semibold mb-1">Как контролировать</div>
            <div class="text-muted">KPI: простои, холостые пробеги, SLA перепланирования (≤15 мин), качество выполнения задания (90%).</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="card border shadow-sm mb-4">
  <div class="card-body">
    <div class="table-responsive">
      <table class="table align-middle mb-0">
        <thead>
          <tr>
            <th style="width:70px;">ID</th>
            <th style="min-width:260px;">Функция/узел</th>
            <th style="min-width:260px;">Зависит от</th>
            <th style="min-width:220px;">Если зависимость “плохая”</th>
            <th style="min-width:220px;">Влияние (impact)</th>
            <th style="min-width:260px;">Что делаем (меры)</th>
            <th style="min-width:260px;">Как контролируем (метрики/сигналы)</th>
          </tr>
        </thead>

        <tbody>

          <tr>
            <td><span class="badge text-bg-light border">D1</span></td>
            <td>
              <div class="fw-semibold">Маршрут на карте / полосы / трек</div>
              <div class="text-muted small">Выдача задания механизатору</div>
            </td>
            <td>
              <ul class="mb-0">
                <li><strong>Границы поля</strong> (ручной ввод: поле/границы)</li>
                <li><strong>GPS</strong> (системы автовождения)</li>
              </ul>
            </td>
            <td class="text-muted">
              Граница неверная / GPS дрейфует / пропуски → маршрут “уезжает”, полосы не совпадают.
            </td>
            <td class="text-muted">
              Рост холостых пробегов, срыв таймингов, падение качества выполнения задания.
            </td>
            <td>
              Валидация геометрии поля; версия/история границ; пороги качества GPS и деградация логики при плохом сигнале.
            </td>
            <td>
              <div>• % полей с валидной геометрией</div>
              <div>• % GPS-точек с плохим качеством / “без GPS”</div>
              <div>• отклонение трека от плана</div>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">D2</span></td>
            <td>
              <div class="fw-semibold">Определение очередности уборки</div>
              <div class="text-muted small">Алгоритм приоритизации</div>
            </td>
            <td>
              <ul class="mb-0">
                <li>Сменное задание (ручной ввод)</li>
                <li>Состояние уборки / прогресс</li>
                <li>Ограничения по ресурсам (наличие техники)</li>
              </ul>
            </td>
            <td class="text-muted">
              Ввод неполный/неактуальный → очередь неверная.
            </td>
            <td class="text-muted">
              Неправильное распределение техники и времени → простои / потери темпа.
            </td>
            <td>
              Обязательные поля и проверки сменного задания; лог изменений; ограничение прав на редактирование.
            </td>
            <td>
              <div>• число правок задания после старта</div>
              <div>• доля “конфликтных” заданий (проверки не пройдены)</div>
              <div>• время на корректировку</div>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">D3</span></td>
            <td>
              <div class="fw-semibold">Оптимизация логистики “комбайн ↔ БП ↔ зерновоз”</div>
              <div class="text-muted small">Расчёт доезда/выгрузки/переезда, сколько комбайнов обслужит БП</div>
            </td>
            <td>
              <ul class="mb-0">
                <li>Телематика: скорость, направление, собранный вес</li>
                <li>Статусы техники и события</li>
              </ul>
            </td>
            <td class="text-muted">
              Телематика неполная/задерживается → расчёты на “плохих” данных.
            </td>
            <td class="text-muted">
              Рост простоев: комбайн ждёт БП/зерновоз или БП “не успевает”.
            </td>
            <td>
              Минимально обязательный набор данных; обработка пропусков; fallback-правила (упрощённые сценарии при нехватке данных).
            </td>
            <td>
              <div>• лаг поступления телематики</div>
              <div>• % событий с пропусками</div>
              <div>• KPI: простои / холостые пробеги</div>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">D4</span></td>
            <td>
              <div class="fw-semibold">Контроль выполнения (карта + статусы)</div>
              <div class="text-muted small">Диспетчерский контур</div>
            </td>
            <td>
              <ul class="mb-0">
                <li>GPS позиция/скорость</li>
                <li>Телематика: события/статусы/поломки</li>
              </ul>
            </td>
            <td class="text-muted">
              Нет актуальных статусов → “картинка” не совпадает с реальностью.
            </td>
            <td class="text-muted">
              Ошибочные управленческие решения, поздняя реакция на простои/поломки.
            </td>
            <td>
              Принудительное обновление статуса при критичных событиях; контроль “старости” данных; сигналы о потере связи/задержках.
            </td>
            <td>
              <div>• доля техники со статусом “не обновлялся &gt; N минут”</div>
              <div>• количество “потерь связи”</div>
              <div>• инциденты по расхождению статуса</div>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">D5</span></td>
            <td>
              <div class="fw-semibold">Диаграмма Ганта (план vs факт)</div>
              <div class="text-muted small">Визуализация работ и загрузки</div>
            </td>
            <td>
              <ul class="mb-0">
                <li>План (сменное задание/тайминг)</li>
                <li>Факт (события/прогресс из телематики)</li>
                <li>Единые идентификаторы техники/смен/операций</li>
              </ul>
            </td>
            <td class="text-muted">
              Нет единой идентификации или “дырки” в факте → Гант вводит в заблуждение.
            </td>
            <td class="text-muted">
              Потеря доверия к плану, невозможность разборов причин простоев.
            </td>
            <td>
              Контракты идентификации; обязательные связи план↔техника↔события; контроль полноты факта.
            </td>
            <td>
              <div>• % задач Ганта, у которых есть “факт”</div>
              <div>• % событий без привязки к смене/технике</div>
              <div>• время реакции диспетчера (операционная метрика)</div>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">D6</span></td>
            <td>
              <div class="fw-semibold">Оповещения по погоде</div>
              <div class="text-muted small">Триггеры и предупреждения</div>
            </td>
            <td>
              <ul class="mb-0">
                <li>Источник прогноза/условий</li>
                <li>Правила: что считается критичным</li>
              </ul>
            </td>
            <td class="text-muted">
              Погода приходит с задержкой или правила “шумят”.
            </td>
            <td class="text-muted">
              Ложные тревоги / пропуск окна — потери темпа уборки.
            </td>
            <td>
              Фильтрация оповещений; пороги; журнал срабатываний; ручное подтверждение в критичных случаях.
            </td>
            <td>
              <div>• % ложных/неподтверждённых оповещений</div>
              <div>• среднее время реакции</div>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">D7</span></td>
            <td>
              <div class="fw-semibold">Перепланирование по погоде</div>
              <div class="text-muted small">Пересчёт графика</div>
            </td>
            <td>
              <ul class="mb-0">
                <li>Погода + правила перестроения</li>
                <li>Актуальный прогресс уборки</li>
              </ul>
            </td>
            <td class="text-muted">
              Переплан не успевает или опирается на старые данные.
            </td>
            <td class="text-muted">
              Срыв сменного задания, потери из-за неправильного решения.
            </td>
            <td>
              SLA на пересчёт и публикацию плана; логирование изменений; фолбэк к базовому плану.
            </td>
            <td>
              <div>• SLA перепланирования: ≤ 15 минут</div>
              <div>• число откатов/перепланов</div>
              <div>• выполнение задания (target 90%)</div>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">D8</span></td>
            <td>
              <div class="fw-semibold">Анализ поломок и логистических задержек</div>
              <div class="text-muted small">Разбор причин простоев</div>
            </td>
            <td>
              <ul class="mb-0">
                <li>Корректная фиксация поломок (телематика/события)</li>
                <li>Классификация причин (справочник)</li>
              </ul>
            </td>
            <td class="text-muted">
              Поломка не фиксируется или классификация “плавающая”.
            </td>
            <td class="text-muted">
              Нельзя управлять простоями и улучшать логистику на данных.
            </td>
            <td>
              Обязательный “минимум” для события поломки; справочник причин; подтверждение диспетчером/инженером.
            </td>
            <td>
              <div>• % поломок с заполненной причиной</div>
              <div>• среднее время реакции на поломку</div>
              <div>• KPI простоев</div>
            </td>
          </tr>

        </tbody>
      </table>
    </div>
  </div>
</div>

<div class="card border">
  <div class="card-body">
    <div class="fw-semibold mb-2">Привязка к KPI (targets)</div>
    <ul class="mb-0">
      <li><strong>Простои:</strong> target −40%</li>
      <li><strong>Холостые пробеги:</strong> target −30%</li>
      <li><strong>Время уборки поля:</strong> target −20%</li>
      <li><strong>Перепланирование:</strong> ≤ 15 минут</li>
      <li><strong>Качество выполнения задания:</strong> 90%</li>
    </ul>
  </div>
</div>
