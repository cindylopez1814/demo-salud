<script setup>
const testimonials = [
  {
    name: 'Valentina R.',
    location: 'São Paulo',
    avatar: 'https://picsum.photos/seed/valentina-r/80/80',
    stars: 5,
    text: 'Há anos eu fazia dietas e vivia no efeito sanfona. Com a Daniela entendi que o problema não era minha força de vontade — era que nunca tive um plano real pra mim. Em 3 meses perdi 8 kg sem passar fome.',
    tag: 'Emagrecimento',
  },
  {
    name: 'Camila T.',
    location: 'Campinas',
    avatar: 'https://picsum.photos/seed/camila-t/80/80',
    stars: 5,
    text: 'Tenho intestino irritável e sempre achei que ia sofrer com a comida a vida toda. A Daniela me ensinou a comer de um jeito que me cuida. Hoje vivo sem as dores constantes que tinha antes.',
    tag: 'Saúde digestiva',
  },
  {
    name: 'Francisca M.',
    location: 'Online · Belo Horizonte',
    avatar: 'https://picsum.photos/seed/francisca-m/80/80',
    stars: 5,
    text: 'Comecei por questões hormonais e acabei transformando minha relação com a comida completamente. O atendimento online foi tão próximo quanto presencial. Recomendo 100%.',
    tag: 'Saúde hormonal',
  },
]
</script>

<template>
  <section class="testimonials" id="depoimentos">
    <div class="container">

      <div class="testimonials__header">
        <span class="section-tag">Depoimentos</span>
        <h2>O que dizem<br /><em>minhas pacientes</em></h2>
      </div>

      <div class="testimonials__grid">
        <article
          v-for="t in testimonials"
          :key="t.name"
          class="testimonial"
        >
          <div class="testimonial__stars">
            <span v-for="n in t.stars" :key="n" class="star">★</span>
          </div>

          <blockquote class="testimonial__text">"{{ t.text }}"</blockquote>

          <span class="testimonial__tag">{{ t.tag }}</span>

          <div class="testimonial__author">
            <img
              :src="t.avatar"
              :alt="t.name"
              class="author__avatar"
              loading="lazy"
            />
            <div>
              <strong class="author__name">{{ t.name }}</strong>
              <span class="author__location">{{ t.location }}</span>
            </div>
          </div>
        </article>
      </div>

      <div class="testimonials__cta">
        <p><em>Pronta para começar a sua jornada?</em></p>
        <a
          href="https://wa.me/5511912345678?text=Oi%20Daniela%2C%20quero%20agendar%20uma%20consulta"
          class="btn-primary"
          target="_blank"
          rel="noopener"
        >
          Agendar minha primeira consulta
        </a>
      </div>

    </div>
  </section>
</template>

<style scoped>
.testimonials {
  background-color: var(--color-surface);
  padding: 100px 0;
}

.testimonials__header {
  text-align: center;
  margin-bottom: 56px;
}

.testimonials__header h2 {
  margin-top: 4px;
}

.testimonials__header h2 em {
  font-family: var(--font-accent);
  font-style: normal;
  color: var(--color-primary);
}

.testimonials__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-bottom: 56px;
}

.testimonial {
  background: var(--color-white);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-lg);
  padding: 32px 28px;
  display: flex;
  flex-direction: column;
  gap: 16px;
  transition: box-shadow var(--transition), transform var(--transition);
}

.testimonial:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-4px);
}

.testimonial__stars { display: flex; gap: 2px; }
.star { color: #F5C842; font-size: 1rem; }

.testimonial__text {
  font-size: 0.93rem;
  line-height: 1.8;
  color: var(--color-text-mid);
  font-style: normal;
  flex-grow: 1;
  letter-spacing: 0.02em;
}

.testimonial__tag {
  display: inline-block;
  font-size: 0.72rem;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  color: var(--color-primary);
  background: var(--color-primary-light);
  padding: 4px 12px;
  border-radius: var(--radius-full);
  align-self: flex-start;
}

.testimonial__author {
  display: flex;
  align-items: center;
  gap: 12px;
  border-top: 1px solid var(--color-border);
  padding-top: 16px;
}

.author__avatar {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  object-fit: cover;
  flex-shrink: 0;
}

.author__name {
  display: block;
  font-size: 0.9rem;
  color: var(--color-text);
  line-height: 1.3;
  letter-spacing: 0.02em;
}

.author__location {
  font-size: 0.78rem;
  color: var(--color-text-light);
}

/* CTA */
.testimonials__cta {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 20px;
  text-align: center;
}

.testimonials__cta p {
  font-family: var(--font-accent);
  font-size: 1.2rem;
  color: var(--color-text);
}

/* ── TABLET ── */
@media (max-width: 900px) {
  .testimonials__grid {
    grid-template-columns: 1fr;
    max-width: 460px;
    margin: 0 auto 48px;
  }
}

/* ── MOBILE ── */
@media (max-width: 480px) {
  .testimonials {
    padding: 64px 0;
  }

  .testimonials__header {
    margin-bottom: 36px;
  }

  .testimonial {
    padding: 24px 20px;
  }

  .testimonials__cta .btn-primary {
    width: 100%;
    justify-content: center;
    padding: 16px 24px;
    font-size: 1rem;
    text-align: center;
  }
}
</style>
