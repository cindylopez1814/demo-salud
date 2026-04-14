<script setup>
const services = [
  {
    icon: '🌱',
    tag: 'Primeira vez',
    name: 'Consulta Inicial',
    description:
      'Avaliação completa dos seus hábitos alimentares, histórico de saúde, exames e objetivos. Criamos juntas um ponto de partida claro e sem julgamentos.',
    duration: '75 min',
    modality: 'Online / Presencial',
    price: 'R$ 280',
    highlight: false,
  },
  {
    icon: '📋',
    tag: 'Mais escolhido',
    name: 'Plano Nutricional',
    description:
      'Plano personalizado de 30 dias com cardápio semanal, receitas adaptadas ao seu estilo de vida, guia de compras e suporte via WhatsApp durante todo o processo.',
    duration: '60 min + plano escrito',
    modality: 'Online / Presencial',
    price: 'R$ 520',
    highlight: true,
  },
  {
    icon: '🔄',
    tag: 'Continuidade',
    name: 'Acompanhamento Mensal',
    description:
      'Ajuste e evolução do seu plano a cada mês. Revisamos resultados, tiramos dúvidas e adaptamos a alimentação às mudanças do seu corpo e rotina.',
    duration: '45 min',
    modality: 'Online / Presencial',
    price: 'R$ 200',
    highlight: false,
  },
]
</script>

<template>
  <section class="services" id="servicos">
    <div class="container">
      <div class="services__header">
        <span class="section-tag">Serviços</span>
        <h2>Como posso<br /><em>te acompanhar?</em></h2>
        <p class="services__sub">
          Cada consulta é um espaço seguro para te ouvir e criar
          um caminho de bem-estar real, no seu ritmo.
        </p>
      </div>

      <div class="services__grid">
        <div
          v-for="service in services"
          :key="service.name"
          :class="['card', { 'card--highlight': service.highlight }]"
        >
          <div class="card__top">
            <div class="card__icon">{{ service.icon }}</div>
            <span class="card__tag">{{ service.tag }}</span>
          </div>

          <h3 class="card__name">{{ service.name }}</h3>
          <p class="card__desc">{{ service.description }}</p>

          <div class="card__meta">
            <div class="meta-item">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/>
              </svg>
              {{ service.duration }}
            </div>
            <div class="meta-item">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/>
              </svg>
              {{ service.modality }}
            </div>
          </div>

          <div class="card__footer">
            <span class="card__price">{{ service.price }}</span>
            <a
              href="https://wa.me/5511912345678"
              target="_blank"
              rel="noopener"
              :class="service.highlight ? 'btn-primary' : 'btn-outline'"
            >
              Agendar
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services {
  background-color: var(--color-bg);
  padding: 100px 0;
}

.services__header {
  text-align: center;
  max-width: 560px;
  margin: 0 auto 56px;
}

.services__header h2 {
  margin-bottom: 16px;
}

.services__header h2 em {
  color: var(--color-accent);
}

.services__sub {
  font-size: 1rem;
  letter-spacing: 0.02em;
}

/* Grid — desktop: 3 col, tablet: 1 col centrado */
.services__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  align-items: start;
}

/* Card */
.card {
  background: var(--color-white);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-lg);
  padding: 32px 28px;
  display: flex;
  flex-direction: column;
  gap: 16px;
  transition: box-shadow var(--transition), transform var(--transition);
}

.card:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-4px);
}

.card--highlight {
  background: var(--color-primary);
  border-color: var(--color-primary);
}

.card--highlight h3,
.card--highlight p,
.card--highlight .meta-item {
  color: rgba(255, 255, 255, 0.9);
}

.card--highlight .card__price { color: var(--color-white); }

.card--highlight .btn-primary {
  background: var(--color-white);
  color: var(--color-primary);
}

.card--highlight .btn-primary:hover {
  background: var(--color-accent-light);
}

.card__top {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.card__icon { font-size: 2rem; line-height: 1; }

.card__tag {
  font-size: 0.72rem;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  color: var(--color-accent);
  background: var(--color-accent-light);
  padding: 4px 10px;
  border-radius: var(--radius-full);
}

.card--highlight .card__tag {
  background: rgba(255,255,255,0.2);
  color: var(--color-white);
}

.card__name { font-size: 1.35rem; letter-spacing: 0.03em; }
.card__desc { font-size: 0.9rem; line-height: 1.7; flex-grow: 1; letter-spacing: 0.02em; }

.card__meta {
  display: flex;
  flex-direction: column;
  gap: 8px;
  border-top: 1px solid var(--color-border);
  border-bottom: 1px solid var(--color-border);
  padding: 14px 0;
}

.card--highlight .card__meta {
  border-color: rgba(255,255,255,0.2);
}

.meta-item {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.82rem;
  color: var(--color-text-mid);
  letter-spacing: 0.02em;
}

.meta-item svg { flex-shrink: 0; color: var(--color-text-light); }

.card__footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
}

.card__price {
  font-family: var(--font-accent);
  font-size: 1.8rem;
  color: var(--color-text);
}

/* ── TABLET ── */
@media (max-width: 960px) {
  .services__grid {
    grid-template-columns: 1fr;
    max-width: 460px;
    margin: 0 auto;
  }
}

/* ── MOBILE ── */
@media (max-width: 480px) {
  .services {
    padding: 64px 0;
  }

  .services__header {
    margin-bottom: 36px;
  }

  .card {
    padding: 24px 20px;
  }

  .card__footer {
    flex-wrap: wrap;
    gap: 12px;
  }

  .card__footer a {
    flex: 1;
    justify-content: center;
    min-width: 0;
  }
}
</style>
