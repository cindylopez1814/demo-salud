<template>
  <section class="about" id="sobre-mim">
    <div class="container about__inner">

      <!-- Imagen -->
      <div class="about__image-wrap">
        <img
          src="/IMG/DOC.png"
          alt="Daniela Mora no consultório"
          class="about__image"
          loading="lazy"
        />
        <div class="about__credential">
          <div class="credential__icon">🎓</div>
          <div>
            <strong>Bacharelado em Nutrição</strong>
            <span>USP São Paulo, 2015</span>
          </div>
        </div>
      </div>

      <!-- Texto -->
      <div class="about__content">
        <span class="section-tag">Sobre mim</span>
        <h2>Sou Daniela,<br /><em>e acredito numa nutrição sem regras rígidas</em></h2>

        <p>
          Há mais de 8 anos acompanho mulheres na sua relação com a alimentação.
          Minha abordagem não é restritiva: trabalho com você para encontrar um
          equilíbrio sustentável que respeite o seu corpo, seus gostos e seu estilo de vida.
        </p>
        <p>
          Especializada em saúde hormonal feminina, síndrome do intestino irritável
          e reeducação alimentar. Cada plano que crio é único — porque você é única.
        </p>

        <div class="about__tags">
          <span class="tag">Saúde hormonal</span>
          <span class="tag">Nutrição funcional</span>
          <span class="tag">Intestino irritável</span>
          <span class="tag">Reeducação alimentar</span>
          <span class="tag">Atendimento online</span>
        </div>

        <div class="about__creds">
          <div class="cred">
            <div class="cred__icon">🏥</div>
            <div>
              <strong>Mestrado em Nutrição Clínica</strong>
              <span>PUC-SP, 2018</span>
            </div>
          </div>
          <div class="cred">
            <div class="cred__icon">📋</div>
            <div>
              <strong>Conselho Federal de Nutricionistas</strong>
              <span>CRN-3 · Registro ativo nº 12.847</span>
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.about {
  background-color: var(--color-surface);
  padding: 100px 0;
}

.about__inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 72px;
  align-items: center;
}

/* Imagen */
.about__image-wrap {
  position: relative;
}

.about__image {
  width: 100%;
  height: 560px;
  object-fit: cover;
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-md);
}

.about__credential {
  position: absolute;
  bottom: -20px;
  right: -20px;
  background: var(--color-accent);
  color: var(--color-white);
  border-radius: var(--radius-lg);
  padding: 16px 22px;
  display: flex;
  align-items: center;
  gap: 12px;
  box-shadow: var(--shadow-accent);
}

.credential__icon { font-size: 1.5rem; }

.about__credential strong {
  display: block;
  font-size: 0.85rem;
  letter-spacing: 0.02em;
  line-height: 1.3;
}

.about__credential span {
  font-size: 0.72rem;
  opacity: 0.8;
}

/* Contenido */
.about__content h2 {
  margin-bottom: 24px;
}

.about__content h2 em {
  color: var(--color-accent);
}

.about__content p + p {
  margin-top: 16px;
}

.about__tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin: 28px 0 32px;
}

.tag {
  display: inline-block;
  padding: 6px 16px;
  background-color: var(--color-accent-light);
  color: var(--color-accent-dark);
  font-size: 0.8rem;
  font-weight: 500;
  letter-spacing: 0.02em;
  border-radius: var(--radius-full);
}

.about__creds {
  display: flex;
  flex-direction: column;
  gap: 16px;
  border-top: 1px solid var(--color-border);
  padding-top: 28px;
}

.cred {
  display: flex;
  align-items: center;
  gap: 14px;
}

.cred__icon { font-size: 1.3rem; flex-shrink: 0; }

.cred strong {
  display: block;
  font-size: 0.9rem;
  color: var(--color-text);
  line-height: 1.3;
  letter-spacing: 0.02em;
}

.cred span {
  font-size: 0.8rem;
  color: var(--color-text-light);
}

/* ── TABLET ── */
@media (max-width: 900px) {
  .about__inner {
    grid-template-columns: 1fr;
    gap: 56px;
  }

  .about__image {
    height: 400px;
  }

  .about__credential {
    right: 0;
    bottom: -16px;
  }
}

/* ── MOBILE ── */
@media (max-width: 480px) {
  .about {
    padding: 64px 0;
  }

  .about__image {
    height: 280px;
    border-radius: var(--radius-md);
  }

  .about__credential {
    right: 0;
    bottom: -14px;
    padding: 12px 16px;
  }

  .about__credential strong { font-size: 0.78rem; }

  .about__content {
    padding-top: 24px;
  }

  .about__tags {
    margin: 20px 0 24px;
  }
}
</style>
