---
title: "Контакты"
permalink: /contact/
id: contact

email: andr@vojtov.ru
telegram: byrnison12
phone: +7 (993) 448-69-80
hh: https://rostov.hh.ru/resume/b4d7a9aaff0ba1a6c80039ed1f656c626b436b
---

# Контакты

<div class="row g-3 mt-1">
  <div class="col-12 col-lg-6">
    <div class="site_contact_card">
      <div class="site_contact_card_title">Связаться</div>

      <div class="site_contact_row">
        <b>Email:</b>
        <a href="mailto:{{ page.email }}">{{ page.email }}</a>
      </div>

      {% assign tg = page.telegram | remove: '@' %}
      <div class="site_contact_row">
        <b>Telegram:</b>
        <a href="https://t.me/{{ tg }}">@{{ tg }}</a>
      </div>

      <div class="site_contact_row">
        <b>Телефон:</b>
          <a href="tel:{{ page.phone | replace: ' ', '' | replace: '(', '' | replace: ')', '' | replace: '-', '' }}">{{ page.phone }}</a>
      </div>

      <div class="mt-3 d-flex flex-wrap gap-2">
        <button type="button" class="btn btn-outline-primary btn-sm" data-bs-toggle="modal" data-bs-target="#contactModal">
          Написать сообщение
        </button>
      </div>
    </div>
  </div>

  <div class="col-12 col-lg-6">
    <div class="site_contact_card">
      <div class="site_contact_card_title">Профили</div>

      {% if page.hh %}
      <div class="site_contact_row">
        <b>HH:</b> <a href="{{ page.hh }}">Резюме</a>
      </div>
      {% endif %}
    </div>
  </div>
</div>

<div class="modal fade" id="contactModal" tabindex="-1" aria-labelledby="contactModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="contactModalLabel">Сообщение</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Закрыть"></button>
      </div>

      <div class="modal-body">
        <div class="alert alert-light border">
          Это статический сайт (GitHub Pages). Форма не отправляет данные — используй Email/Telegram.
        </div>

        <form>
          <div class="mb-3">
            <label class="form-label">Тема</label>
            <input class="form-control" type="text" placeholder="Например: Вакансия PM/PO" />
          </div>

          <div class="mb-3">
            <label class="form-label">Сообщение</label>
            <textarea class="form-control" rows="4" placeholder="Текст..."></textarea>
          </div>

          <a class="btn btn-primary" href="mailto:{{ page.email }}">Открыть письмо</a>
        </form>
      </div>
    </div>
  </div>
</div>
