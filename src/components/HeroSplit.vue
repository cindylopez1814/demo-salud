<template>
  <section class="hero">
    <div class="container hero__inner">

      <!-- Texto -->
      <div class="hero__content">
        <span class="section-tag">Nutricionista Clínica · São Paulo, Brasil</span>
        <h1>Cuide do seu corpo<em>por dentro</em></h1>
        <p class="hero__sub">
          Alimentação consciente e personalizada para mulheres que querem
          viver com energia, equilíbrio e bem-estar de verdade.
        </p>
        <div class="hero__actions">
          <a
            href="https://wa.me/5511912345678?text=Oi%20Daniela%2C%20quero%20agendar%20uma%20consulta"
            class="btn-primary"
            target="_blank"
            rel="noopener"
          >
            <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
              <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/>
              <path d="M12 0C5.373 0 0 5.373 0 12c0 2.127.558 4.126 1.535 5.862L.057 23.928a.5.5 0 00.614.614l6.066-1.478A11.934 11.934 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.807 9.807 0 01-5.003-1.368l-.36-.214-3.724.906.923-3.623-.234-.372A9.818 9.818 0 012.182 12C2.182 6.57 6.57 2.182 12 2.182S21.818 6.57 21.818 12 17.43 21.818 12 21.818z"/>
            </svg>
            Agendar consulta
          </a>
          <a href="#servicos" class="btn-outline">Ver serviços</a>
        </div>

        <!-- Stats -->
        <div class="hero__stats">
          <div class="stat">
            <span class="stat__number">+500</span>
            <span class="stat__label">Pacientes atendidas</span>
          </div>
          <div class="stat__divider"></div>
          <div class="stat">
            <span class="stat__number">8</span>
            <span class="stat__label">Anos de experiência</span>
          </div>
          <div class="stat__divider"></div>
          <div class="stat">
            <span class="stat__number">100%</span>
            <span class="stat__label">Plano personalizado</span>
          </div>
        </div>
      </div>

      <!-- Imagen -->
      <div class="hero__image-wrap">
        <div class="hero__image-bg"></div>
        <img
          src="/IMG/hero.png"
          alt="Daniela Mora, Nutricionista Clínica"
          class="hero__image"
          loading="eager"
        />
        <div class="hero__badge">
          <span class="badge__icon">🌿</span>
          <div>
            <strong>Atendimento presencial</strong>
            <span>e online disponível</span>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.hero {
  background-color: var(--color-bg);
  padding: 80px 0 100px;
  overflow: hidden;
}

.hero__inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 64px;
  align-items: center;
}

.hero__content h1 {
  margin-bottom: 20px;
}

.hero__content h1 em {
  color: var(--color-accent);
}

.hero__sub {
  font-size: 1.05rem;
  max-width: 480px;
  margin-bottom: 36px;
  letter-spacing: 0.02em;
}

.hero__actions {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
  margin-bottom: 44px;
}

/* Stats */
.hero__stats {
  display: flex;
  align-items: center;
  gap: 24px;
}

.stat {
  display: flex;
  flex-direction: column;
}

.stat__number {
  font-family: var(--font-accent);
  font-size: 2rem;
  color: var(--color-text);
  line-height: 1;
}

.stat__label {
  font-size: 0.78rem;
  color: var(--color-text-light);
  margin-top: 4px;
  letter-spacing: 0.03em;
}

.stat__divider {
  width: 1px;
  height: 36px;
  background-color: var(--color-border);
}

/* Imagen */
.hero__image-wrap {
  position: relative;
}

.hero__image-bg {
  position: absolute;
  inset: 24px -24px -24px 24px;
  background-color: var(--color-accent-light);
  border-radius: var(--radius-xl);
  z-index: 0;
}

.hero__image {
  position: relative;
  z-index: 1;
  width: 100%;
  height: 580px;
  object-fit: cover;
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-lg);
}

.hero__badge {
  position: absolute;
  z-index: 2;
  bottom: 32px;
  left: -24px;
  background: var(--color-white);
  border-radius: var(--radius-md);
  padding: 14px 20px;
  display: flex;
  align-items: center;
  gap: 12px;
  box-shadow: var(--shadow-md);
}

.badge__icon { font-size: 1.6rem; }

.hero__badge strong {
  display: block;
  font-size: 0.85rem;
  color: var(--color-text);
  line-height: 1.2;
  letter-spacing: 0.02em;
}

.hero__badge span {
  font-size: 0.75rem;
  color: var(--color-text-light);
}

/* ── TABLET ── */
@media (max-width: 900px) {
  .hero {
    padding: 56px 0 72px;
  }

  .hero__inner {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .hero__image-wrap {
    order: -1;
  }

  .hero__image {
    height: 400px;
  }

  .hero__image-bg {
    inset: 12px -12px -12px 12px;
  }

  .hero__badge {
    left: 12px;
    bottom: 20px;
    padding: 12px 16px;
  }
}

/* ── MOBILE ── */
@media (max-width: 480px) {
  .hero {
    padding: 44px 0 60px;
  }

  .hero__image {
    height: 300px;
    border-radius: var(--radius-md);
  }

  .hero__image-bg {
    display: none;
  }

  .hero__badge {
    left: 50%;
    transform: translateX(-50%);
    bottom: -20px;
    white-space: nowrap;
  }

  .hero__content {
    padding-top: 36px;
  }

  .hero__actions {
    flex-direction: column;
    gap: 10px;
    margin-bottom: 36px;
  }

  .hero__actions a {
    width: 100%;
    justify-content: center;
    padding: 16px 24px;
    font-size: 1rem;
  }

  .hero__stats {
    gap: 0;
    justify-content: space-between;
  }

  .stat__divider {
    display: block;
  }

  .stat__number {
    font-size: 1.6rem;
  }
}
</style>
