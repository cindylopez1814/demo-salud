<script setup>
const steps = [
  {
    number: '01',
    icon: '📅',
    title: 'Você agenda a consulta',
    description:
      'Reserve pelo WhatsApp ou formulário. Confirmo em menos de 24 horas e envio um questionário prévio para aproveitarmos melhor nosso tempo juntas.',
  },
  {
    number: '02',
    icon: '🔍',
    title: 'Avaliação completa',
    description:
      'Na primeira sessão revisamos seus exames, hábitos, histórico clínico e objetivos. Sem julgamentos, com escuta de verdade.',
  },
  {
    number: '03',
    icon: '📋',
    title: 'Seu plano personalizado',
    description:
      'Crio um plano nutricional adaptado a você: seus gostos, horários, orçamento e necessidades específicas. Nada genérico.',
  },
  {
    number: '04',
    icon: '🌿',
    title: 'Acompanhamento contínuo',
    description:
      'Acompanhamento mensal para ajustar o plano e celebrar suas conquistas. Estou disponível pelo WhatsApp entre as sessões.',
  },
]
</script>

<template>
  <section class="steps" id="processo">
    <div class="container">

      <div class="steps__header">
        <span class="section-tag">Como trabalhamos</span>
        <h2>Como trabalhamos<br /><em>juntas</em></h2>
      </div>

      <!-- Desktop: horizontal. Mobile: vertical com linha lateral -->
      <div class="steps__grid">
        <div
          v-for="(step, index) in steps"
          :key="step.number"
          class="step"
        >
          <div class="step__number-wrap">
            <div class="step__number">{{ step.number }}</div>
            <div v-if="index < steps.length - 1" class="step__connector"></div>
          </div>
          <div class="step__body">
            <div class="step__icon">{{ step.icon }}</div>
            <h3 class="step__title">{{ step.title }}</h3>
            <p class="step__desc">{{ step.description }}</p>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.steps {
  background-color: var(--color-primary);
  padding: 100px 0;
  position: relative;
  overflow: hidden;
}

.steps::before {
  content: '';
  position: absolute;
  top: -120px; right: -120px;
  width: 400px; height: 400px;
  border-radius: 50%;
  background: rgba(255,255,255,0.04);
  pointer-events: none;
}

.steps::after {
  content: '';
  position: absolute;
  bottom: -80px; left: -80px;
  width: 280px; height: 280px;
  border-radius: 50%;
  background: rgba(255,255,255,0.04);
  pointer-events: none;
}

/* Header */
.steps__header {
  text-align: center;
  margin-bottom: 64px;
}

.steps__header .section-tag {
  color: rgba(255,255,255,0.55);
}

.steps__header h2 {
  color: var(--color-white);
  letter-spacing: 0.04em;
}

.steps__header h2 em {
  font-family: var(--font-accent);
  font-style: normal;
  color: rgba(255,255,255,0.55);
}

/* Grid desktop */
.steps__grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
  position: relative;
}

.step {
  padding: 0 20px;
  text-align: center;
  position: relative;
}

.step__number-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  position: relative;
}

.step__number {
  width: 52px;
  height: 52px;
  border-radius: 50%;
  background: rgba(255,255,255,0.12);
  border: 1.5px solid rgba(255,255,255,0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-accent);
  font-size: 1.1rem;
  color: var(--color-white);
  flex-shrink: 0;
  z-index: 1;
}

.step__connector {
  position: absolute;
  top: 50%;
  left: calc(50% + 26px);
  right: calc(-50% + 26px);
  height: 1px;
  background: rgba(255,255,255,0.2);
  transform: translateY(-50%);
}

.step__icon { font-size: 2rem; margin-bottom: 16px; }
.step__title { color: var(--color-white); font-size: 1.1rem; margin-bottom: 12px; letter-spacing: 0.03em; }
.step__desc { color: rgba(255,255,255,0.72); font-size: 0.88rem; line-height: 1.7; letter-spacing: 0.02em; }

/* ── TABLET ── */
@media (max-width: 900px) {
  .steps__grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 48px 24px;
  }

  .step__connector {
    display: none;
  }
}

/* ── MOBILE ── layout vertical com linha lateral ── */
@media (max-width: 540px) {
  .steps {
    padding: 64px 0;
  }

  .steps__header {
    margin-bottom: 44px;
  }

  .steps__grid {
    grid-template-columns: 1fr;
    gap: 0;
    max-width: 360px;
    margin: 0 auto;
    padding-left: 12px;
  }

  .step {
    display: flex;
    text-align: left;
    padding: 0 0 36px 0;
    gap: 20px;
    position: relative;
  }

  /* Línea lateral continua */
  .step:not(:last-child)::before {
    content: '';
    position: absolute;
    left: 24px;
    top: 52px;
    bottom: 0;
    width: 1px;
    background: rgba(255,255,255,0.2);
  }

  .step__number-wrap {
    flex-direction: column;
    margin-bottom: 0;
    flex-shrink: 0;
  }

  .step__connector {
    display: none;
  }

  .step__number {
    width: 48px;
    height: 48px;
  }

  .step__body {
    padding-top: 8px;
  }

  .step__icon {
    font-size: 1.5rem;
    margin-bottom: 8px;
  }

  .step__title {
    font-size: 1rem;
    margin-bottom: 8px;
  }
}
</style>
