---
title: "Контакты"
permalink: /contact/
email: "andr@vojtov.ru"
telegram: "@byrnison12"
telegram_url: "https://t.me/byrnison12"
phone: "+7 (993) 448-69-80"
hh_url: "https://rostov.hh.ru/resume/b4d7a9aaff0ba1a6c80039ed1f656c626b436b"
---


# Контакты

<div class="row g-3 mt-1">
  <div class="col-12 col-lg-7">
    <div class="card shadow-sm h-100 rounded-4">
      <div class="card-body p-4">
        <div class="fw-semibold mb-2">Связаться</div>

        <div class="mb-2"><b>Email:</b> <a href="mailto:{{ page.email }}">{{ page.email }}</a></div>
        <div class="mb-2"><b>Telegram:</b> <a href="https://t.me/{{ page.telegram }}">{{ page.telegram }}</a></div>
        <div class="mb-3"><b>Телефон:</b> <a href="tel:{{ page.phone | replace:' ', '' }}">{{ page.phone }}</a></div>
      </div>
    </div>
  </div>

  <div class="col-12 col-lg-5">
    <div class="card shadow-sm h-100 rounded-4">
      <div class="card-body p-4">
        <div class="fw-semibold mb-2">Профили</div>
        <div class="mb-2"><b>HH:</b> <a href="https://rostov.hh.ru/resume/b4d7a9aaff0ba1a6c80039ed1f656c626b436b">Резюме</a></div>
      </div>
    </div>
  </div>
</div>

<!-- Modal -->
<div class="modal fade" id="msgModal" tabindex="-1" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content rounded-4">
      <div class="modal-header">
        <h5 class="modal-title">Сообщение</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
    </div>
  </div>
</div>

<script>
function openMail(){
  const to = "{{ page.email }}";
  const s = encodeURIComponent(document.getElementById('mailSubject').value || 'Сообщение с сайта');
  const b = encodeURIComponent(document.getElementById('mailBody').value || '');
  window.location.href = `mailto:${to}?subject=${s}&body=${b}`;
}
</script>
