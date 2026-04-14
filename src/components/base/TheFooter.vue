<template>
  <footer class="footer">
    <div class="footer__inner">
      <span class="footer__brand">Daniela Mora Nutrição</span>
      <span class="footer__copy">© 2025 Daniela Mora — Nutricionista Clínica · São Paulo, Brasil</span>
      <span class="footer__tagline">Feito com ❤️ para o seu bem-estar</span>
    </div>
    <div class="footer__built">
      <span class="footer__built-text">BUILT BY <a href="https://calolab.com.br" target="_blank" rel="noopener" class="footer__built-link">CALO LAB</a></span>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: var(--color-primary);
  border-top: 1px solid rgba(255, 255, 255, 0.08);
}

.footer__inner {
  max-width: var(--container);
  margin: 0 auto;
  padding: 32px 28px;
  display: flex;
  align-items: center;
  gap: 32px;
  flex-wrap: wrap;
}

.footer__brand {
  font-size: 0.95rem;
  font-weight: 700;
  color: var(--color-white);
  letter-spacing: 0.01em;
}

.footer__copy {
  font-size: 0.82rem;
  color: rgba(255, 255, 255, 0.45);
  flex: 1;
  text-align: center;
}

.footer__tagline {
  font-size: 0.82rem;
  color: rgba(255, 255, 255, 0.45);
}

.footer__built {
  border-top: 1px solid rgba(255, 255, 255, 0.06);
  text-align: center;
  padding: 12px 28px;
}

.footer__built-text {
  font-family: 'Courier New', monospace;
  font-size: 10px;
  font-weight: 500;
  letter-spacing: 2px;
  color: rgba(255, 255, 255, 0.45);
  text-transform: uppercase;
}

.footer__built-link {
  font-family: 'Courier New', monospace;
  color: var(--color-accent);
  text-decoration: none;
  transition: opacity 0.2s ease;
}

.footer__built-link:hover {
  opacity: 0.75;
}

@media (max-width: 768px) {
  .footer__inner {
    flex-direction: column;
    text-align: center;
    padding: 28px 20px;
    gap: 10px;
  }

  .footer__copy {
    text-align: center;
  }

  .footer__built {
    padding: 12px 20px;
  }
}
</style>
