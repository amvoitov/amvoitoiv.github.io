---
title: "Контакты"
permalink: /contact/

email: "andr@vojtov.ru"
telegram: "@byrnison12"
telegram_url: "https://t.me/byrnison12"

phone: "+7 (993) 448-69-80"
phone_tel: "+79934486980"

hh_url: "ВСТАВЬ_ССЫЛКУ_НА_HH"
---

# Контакты

<div class="row g-3">
  <div class="col-12 col-lg-6">
    <div class="card h-100 shadow-sm">
      <div class="card-body">
        <h5 class="card-title mb-3">Связаться</h5>

        <div class="mb-2"><b>Email:</b> <a href="mailto:{{ page.email }}">{{ page.email }}</a></div>
        <div class="mb-2"><b>Telegram:</b> <a href="{{ page.telegram_url }}" target="_blank" rel="noopener">{{ page.telegram }}</a></div>
        <div class="mb-2"><b>Телефон:</b> <a href="tel:{{ page.phone_tel }}">{{ page.phone }}</a></div>

        <button class="btn btn-outline-primary mt-3" data-bs-toggle="modal" data-bs-target="#contactModal">
          Написать сообщение
        </button>
      </div>
    </div>
  </div>

  <div class="col-12 col-lg-6">
    <div class="card h-100 shadow-sm">
      <div class="card-body">
        <h5 class="card-title mb-3">Профили</h5>
        <div class="mb-2"><b>HH:</b> <a href="{{ page.hh_url }}" target="_blank" rel="noopener">Резюме</a></div>
      </div>
    </div>
  </div>
</div>

<!-- Modal -->
<div class="modal fade" id="contactModal" tabindex="-1" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">Сообщение</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Закрыть"></button>
      </div>

      <div class="modal-body">
        <div class="alert alert-light border mb-3">
          Это статический сайт. Кнопка откроет письмо в вашем почтовом клиенте (Email/Telegram).
        </div>

        <div class="mb-3">
          <label class="form-label">Тема</label>
          <input id="mailSubject" class="form-control" placeholder="Например: Вакансия PM/PO">
        </div>

        <div class="mb-3">
          <label class="form-label">Сообщение</label>
          <textarea id="mailBody" class="form-control" rows="5" placeholder="Текст..."></textarea>
        </div>
      </div>

      <div class="modal-footer">
        <button type="button" class="btn btn-primary" id="openMailBtn">Открыть письмо</button>
      </div>
    </div>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {
  const btn = document.getElementById('openMailBtn');
  if (!btn) return;

  btn.addEventListener('click', () => {
    const subject = encodeURIComponent(document.getElementById('mailSubject')?.value || 'Вакансия PM/PO');
    const body = encodeURIComponent(document.getElementById('mailBody')?.value || '');
    const to = "{{ page.email }}";
    window.location.href = `mailto:${to}?subject=${subject}&body=${body}`;
  });
});
</script>
