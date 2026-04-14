<script setup>
import { ref } from 'vue'

const form = ref({ name: '', email: '', message: '' })
const sent = ref(false)

function handleSubmit() {
  sent.value = true
  form.value = { name: '', email: '', message: '' }
  setTimeout(() => { sent.value = false }, 4000)
}
</script>

<template>
  <section class="contact" id="contato">
    <div class="container contact__inner">

      <!-- Info -->
      <div class="contact__info">
        <span class="section-tag">Contato</span>
        <h2>Vamos conversar?</h2>
        <p>
          Se você tem dúvidas sobre algum serviço ou quer saber se posso
          te ajudar, me escreva. Respondo pessoalmente, sem assistentes.
        </p>

        <a
          href="https://wa.me/5511912345678?text=Oi%20Daniela%2C%20gostaria%20de%20informações%20sobre%20seus%20serviços"
          class="whatsapp-btn"
          target="_blank"
          rel="noopener"
        >
          <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor">
            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/>
            <path d="M12 0C5.373 0 0 5.373 0 12c0 2.127.558 4.126 1.535 5.862L.057 23.928a.5.5 0 00.614.614l6.066-1.478A11.934 11.934 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.807 9.807 0 01-5.003-1.368l-.36-.214-3.724.906.923-3.623-.234-.372A9.818 9.818 0 012.182 12C2.182 6.57 6.57 2.182 12 2.182S21.818 6.57 21.818 12 17.43 21.818 12 21.818z"/>
          </svg>
          Falar pelo WhatsApp
        </a>

        <div class="contact__details">
          <div class="detail">
            <span class="detail__icon">📍</span>
            <div>
              <strong>Consultório</strong>
              <span>Pinheiros, São Paulo (presencial)</span>
            </div>
          </div>
          <div class="detail">
            <span class="detail__icon">💻</span>
            <div>
              <strong>Atendimento online</strong>
              <span>Para todo o Brasil</span>
            </div>
          </div>
          <div class="detail">
            <span class="detail__icon">🕐</span>
            <div>
              <strong>Horário de atendimento</strong>
              <span>Segunda a sexta, 9h–18h</span>
            </div>
          </div>
          <div class="detail">
            <span class="detail__icon">✉️</span>
            <div>
              <strong>E-mail</strong>
              <span>daniela@nutricaomora.com.br</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Formulario -->
      <div class="contact__form-wrap">
        <div v-if="sent" class="form-success">
          <span class="success-icon">✅</span>
          <h3>Mensagem enviada!</h3>
          <p>Vou te responder em breve. Se precisar de retorno mais rápido, me manda uma mensagem no WhatsApp.</p>
        </div>

        <form v-else class="form" @submit.prevent="handleSubmit">
          <h3 class="form__title">Envie uma mensagem</h3>

          <div class="field">
            <label for="name" class="field__label">Seu nome</label>
            <input
              id="name"
              v-model="form.name"
              type="text"
              class="field__input"
              placeholder="Como você se chama?"
              required
            />
          </div>

          <div class="field">
            <label for="email" class="field__label">Seu e-mail</label>
            <input
              id="email"
              v-model="form.email"
              type="email"
              class="field__input"
              placeholder="voce@email.com"
              required
            />
          </div>

          <div class="field">
            <label for="message" class="field__label">Me conta</label>
            <textarea
              id="message"
              v-model="form.message"
              class="field__input field__textarea"
              placeholder="Em que posso te ajudar? Tem alguma dúvida específica?"
              rows="5"
              required
            ></textarea>
          </div>

          <button type="submit" class="btn-primary form__submit">
            Enviar mensagem
          </button>

          <p class="form__note">
            Respondo em menos de 24 horas úteis.
          </p>
        </form>
      </div>

    </div>

    <div class="footer">
      <div class="container">
        <p>© 2025 Daniela Mora — Nutricionista Clínica · Feito com ♡ por <strong>Calo Lab</strong></p>
      </div>
    </div>

  </section>
</template>

<style scoped>
.contact {
  background-color: var(--color-bg);
  padding-top: 100px;
}

.contact__inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 72px;
  align-items: start;
  padding-bottom: 100px;
}

.contact__info h2 {
  margin-bottom: 16px;
}

.contact__info > p {
  margin-bottom: 32px;
  max-width: 420px;
  letter-spacing: 0.02em;
}

.whatsapp-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 14px 28px;
  background-color: #25D366;
  color: var(--color-white);
  font-family: var(--font-body);
  font-size: 0.9rem;
  letter-spacing: 0.03em;
  border-radius: var(--radius-full);
  margin-bottom: 36px;
  transition: background-color var(--transition), transform var(--transition);
}

.whatsapp-btn:hover {
  background-color: #1da851;
  transform: translateY(-2px);
}

.contact__details {
  display: flex;
  flex-direction: column;
  gap: 20px;
  border-top: 1px solid var(--color-border);
  padding-top: 28px;
}

.detail {
  display: flex;
  align-items: center;
  gap: 14px;
}

.detail__icon {
  font-size: 1.2rem;
  flex-shrink: 0;
  width: 32px;
  text-align: center;
}

.detail strong {
  display: block;
  font-size: 0.88rem;
  color: var(--color-text);
  line-height: 1.3;
  letter-spacing: 0.02em;
}

.detail span {
  font-size: 0.82rem;
  color: var(--color-text-light);
}

/* Formulario */
.contact__form-wrap {
  background: var(--color-white);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-lg);
  padding: 40px 36px;
  box-shadow: var(--shadow-sm);
}

.form__title {
  font-size: 1.5rem;
  letter-spacing: 0.04em;
  margin-bottom: 28px;
}

.form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.field {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.field__label {
  font-size: 0.85rem;
  color: var(--color-text);
  letter-spacing: 0.03em;
}

.field__input {
  width: 100%;
  padding: 14px 16px;
  border: 1.5px solid var(--color-border);
  border-radius: var(--radius-sm);
  font-family: var(--font-body);
  font-size: 0.9rem;
  color: var(--color-text);
  background: var(--color-bg);
  transition: border-color var(--transition), box-shadow var(--transition);
  outline: none;
  resize: none;
  letter-spacing: 0.02em;
  /* touch-friendly */
  -webkit-appearance: none;
  appearance: none;
}

.field__input::placeholder {
  color: var(--color-text-light);
}

.field__input:focus {
  border-color: var(--color-primary);
  box-shadow: 0 0 0 3px var(--color-primary-light);
  background: var(--color-white);
}

.field__textarea {
  min-height: 120px;
  resize: vertical;
}

.form__submit {
  width: 100%;
  justify-content: center;
  padding: 16px;
  font-size: 1rem;
}

.form__note {
  font-size: 0.78rem;
  text-align: center;
  color: var(--color-text-light);
  margin: 0;
  letter-spacing: 0.02em;
}

/* Success */
.form-success {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  gap: 12px;
  min-height: 300px;
  padding: 24px;
}

.success-icon { font-size: 3rem; }

.form-success h3 {
  font-size: 1.6rem;
  letter-spacing: 0.04em;
}

.form-success p {
  max-width: 320px;
  letter-spacing: 0.02em;
}

/* Footer */
.footer {
  border-top: 1px solid var(--color-border);
  padding: 24px 0;
}

.footer p {
  font-size: 0.82rem;
  text-align: center;
  color: var(--color-text-light);
  letter-spacing: 0.02em;
}

.footer strong {
  color: var(--color-primary);
}

/* ── TABLET ── */
@media (max-width: 900px) {
  .contact__inner {
    grid-template-columns: 1fr;
    gap: 48px;
  }
}

/* ── MOBILE ── */
@media (max-width: 480px) {
  .contact {
    padding-top: 64px;
  }

  .contact__inner {
    padding-bottom: 64px;
  }

  .whatsapp-btn {
    width: 100%;
    justify-content: center;
    padding: 16px 24px;
    font-size: 1rem;
    margin-bottom: 28px;
  }

  .contact__form-wrap {
    padding: 28px 20px;
  }

  .field__input {
    font-size: 16px; /* evita zoom automático en iOS */
    padding: 16px;
  }
}
</style>
