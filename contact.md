---
title: "Контакты"
permalink: /contact/
id: contact

email: you@mail.com
telegram: yourname
hh: https://hh.ru/resume/XXXXXXXXXXXX
github: https://github.com/amvoitov
---

# Контакты

<div class="row g-3 mt-1">
  <div class="col-12 col-lg-6">
    <div class="site_contact_card">
      <div class="site_contact_card_title">Связаться</div>
      <div class="site_contact_row"><b>Email:</b> <a href="mailto:andr@vojtov.ru">andr@vojtov.ru</a></div>
      <div class="site_contact_row"><b>Telegram:</b> <a href="https://t.me/byrnison12">@byrnison12</a></div>

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
      <div class="site_contact_row"><b>HH:</b> <a href="https://rostov.hh.ru/resume/b4d7a9aaff0ba1a6c80039ed1f656c626b436b">Резюме</a></div>
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

          <a class="btn btn-primary" href="mailto:you@mail.com">Открыть письмо</a>
        </form>
      </div>
    </div>
  </div>
</div>
