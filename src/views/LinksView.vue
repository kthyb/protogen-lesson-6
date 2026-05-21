<script setup lang="ts">
const links = [
  { label: 'Portfolio', href: 'https://example.com', icon: '🌾' },
  { label: 'Dribbble', href: 'https://dribbble.com', icon: '🎨' },
  { label: 'LinkedIn', href: 'https://linkedin.com', icon: '💼' },
  { label: 'Email', href: 'mailto:hello@example.com', icon: '✉️' },
]
</script>

<template>
  <main class="page">
    <section class="card">
      <div class="card-inner">
        <h1 class="name">Brooke Jackson</h1>
        <p class="tagline">Designer · Developer · Adventurer of the Valley</p>

        <ul class="links">
          <li v-for="link in links" :key="link.label">
            <a class="link-btn" :href="link.href" target="_blank" rel="noopener">
              <span class="link-icon" aria-hidden="true">{{ link.icon }}</span>
              <span class="link-label">{{ link.label }}</span>
            </a>
          </li>
        </ul>

        <footer class="footer">~ welcome to the farm ~</footer>
      </div>
    </section>
  </main>
</template>

<style scoped>
.page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem 1rem;
}

.card {
  width: 100%;
  max-width: 480px;
  background: var(--sv-parchment);
  border: 4px solid var(--sv-brown-dark);
  border-radius: 6px;
  box-shadow:
    0 0 0 4px var(--sv-brown-light) inset,
    6px 6px 0 0 var(--sv-shadow);
  padding: 6px;
}

.card-inner {
  border: 2px dashed var(--sv-brown-mid);
  border-radius: 3px;
  padding: 1.75rem 1.25rem 1.25rem;
  text-align: center;
}

.name {
  font-family: 'Roboto Mono', monospace;
  font-weight: 700;
  font-size: 1.75rem;
  letter-spacing: 0.04em;
  color: var(--sv-brown-dark);
  text-shadow: 2px 2px 0 var(--sv-cream);
  margin: 0 0 0.4rem;
  text-transform: uppercase;
}

.tagline {
  font-size: 0.9rem;
  color: var(--sv-brown-mid);
  margin: 0 0 1.5rem;
  font-style: italic;
}

.links {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.link-btn {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  width: 100%;
  padding: 0.85rem 1rem;
  background: var(--sv-green);
  color: var(--sv-cream);
  text-decoration: none;
  font-weight: 700;
  font-size: 0.95rem;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  border: 3px solid var(--sv-brown-dark);
  border-radius: 4px;
  box-shadow:
    0 0 0 2px var(--sv-green-light) inset,
    4px 4px 0 0 var(--sv-shadow);
  transition: transform 0.08s ease, box-shadow 0.08s ease, background 0.15s ease;
}

.link-btn:hover {
  background: var(--sv-green-light);
  color: var(--sv-brown-dark);
}

.link-btn:active {
  transform: translate(4px, 4px);
  box-shadow:
    0 0 0 2px var(--sv-green-light) inset,
    0 0 0 0 var(--sv-shadow);
}

.link-icon {
  font-size: 1.1rem;
}

.link-label {
  flex: 1;
  text-align: center;
}

.footer {
  margin-top: 1.75rem;
  font-size: 0.8rem;
  color: var(--sv-brown-mid);
  letter-spacing: 0.1em;
}
</style>
