<template>
  <footer class="site-footer">
    <div class="container">
      <div class="fgrid">
        <div>
          <div class="brand">
            <img
              src="https://is3.cloudhost.id/konnetto-asset/konnetto-logo.jpeg"
              alt="Konnetto logo"
            />
            <span>Konnetto</span>
          </div>
          <p class="fdesc">
            A niche social platform for fans & creators of Japanese culture.
          </p>
        </div>

        <div class="fcol">
          <h4>Platform</h4>
          <a href="#about">About</a>
          <a href="#benefits">Features</a>
          <a href="#early">Roadmap</a>
        </div>

        <div class="fcol">
          <h4>Legal</h4>
          <a href="#">Privacy</a>
          <a href="#">Terms</a>
          <a href="#">Cookies</a>
        </div>

        <div class="fcol connect-col">
          <h4>Connect</h4>

          <!-- Socials: inline SVG (no CDN) -->
          <p class="socials" aria-label="Social links">
            <!-- X / Twitter -->
            <a href="#" class="social-link" aria-label="Twitter / X">
              <svg viewBox="0 0 24 24" aria-hidden="true">
                <path fill="currentColor"
                  d="M18.244 2 12.9 8.14 8.48 2H2.5l7.27 9.9L2 22h5.52l5-6.3L16.12 22h5.88l-7.64-10.4L22 2h-3.756Z"/>
              </svg>
            </a>

            <!-- Instagram -->
            <a href="#" class="social-link" aria-label="Instagram">
              <svg viewBox="0 0 24 24" aria-hidden="true">
                <path fill="currentColor"
                  d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5Zm0 2a3 3 0 0 0-3 3v10a3 3 0 0 0 3 3h10a3 3 0 0 0 3-3V7a3 3 0 0 0-3-3H7Zm5 3.5a5.5 5.5 0 1 1 0 11 5.5 5.5 0 0 1 0-11Zm0 2a3.5 3.5 0 1 0 0 7 3.5 3.5 0 0 0 0-7ZM18 6.2a1.2 1.2 0 1 0 0 2.4 1.2 1.2 0 0 0 0-2.4Z"/>
              </svg>
            </a>

            <!-- TikTok -->
            <a href="#" class="social-link" aria-label="TikTok">
              <svg viewBox="0 0 24 24" aria-hidden="true">
                <path fill="currentColor"
                  d="M16.6 2c.4 2.2 1.7 3.9 3.6 4.7V10c-1.4-.1-2.8-.6-3.6-1.3v7.4c0 3.9-2.8 6.4-6.6 6.4S3.4 20.1 3.4 16.2c0-4 3-7 7.1-7 .4 0 .9 0 1.3.1v3.5c-.4-.1-.9-.2-1.3-.2-2 0-3.6 1.5-3.6 3.5s1.6 3.7 3.6 3.7c2 0 3.3-1 3.3-3.2V2h2.4Z"/>
              </svg>
            </a>

            <!-- Discord -->
            <a href="#" class="social-link" aria-label="Discord">
              <svg viewBox="0 0 24 24" aria-hidden="true">
                <path fill="currentColor"
                  d="M20 4.5A17.2 17.2 0 0 0 15.6 3l-.3.5c1.7.4 2.7 1 3.5 1.6A10.8 10.8 0 0 0 12 4c-2.1 0-3.6.6-4.7 1 1-.7 1.8-1.2 3.5-1.6L10.6 3A17.2 17.2 0 0 0 6 4.5C3.6 7.9 3 11.1 3.2 14.3c1.2 1.3 3 2.1 4.9 2.6l.6-.9c-.8-.3-1.6-.7-2.3-1.2l.6-.5c4.4 2 9.1 2 13.4 0l.6.5c-.7.5-1.5.9-2.3 1.2l.6.9c1.9-.5 3.7-1.3 4.9-2.6.2-3.2-.4-6.4-2.8-9.8ZM9.5 13.6a1.7 1.7 0 1 1 0-3.4 1.7 1.7 0 0 1 0 3.4Zm5 0a1.7 1.7 0 1 1 0-3.4 1.7 1.7 0 0 1 0 3.4Z"/>
              </svg>
            </a>

            <!-- YouTube -->
            <a href="#" class="social-link" aria-label="YouTube">
              <svg viewBox="0 0 24 24" aria-hidden="true">
                <path fill="currentColor"
                  d="M23 12c0-2.3-.2-3.8-.6-4.6a3.3 3.3 0 0 0-2-2.1C19.5 5 12 5 12 5S4.5 5 3.6 5.3a3.3 3.3 0 0 0-2 2.1C1.2 8.2 1 9.7 1 12s.2 3.8.6 4.6a3.3 3.3 0 0 0 2 2.1C4.5 19 12 19 12 19s7.5 0 8.4-.3a3.3 3.3 0 0 0 2-2.1c.4-.8.6-2.3.6-4.6ZM10 15.2V8.8l5.3 3.2L10 15.2Z"/>
              </svg>
            </a>
          </p>

          <a href="mailto:info@konnetto.co" class="footer-email">info@konnetto.co</a>
        </div>
      </div>

      <div class="footer-divider"></div>

      <div class="copyright">
        © <span id="year">2025</span> Konnetto. All rights reserved.
      </div>
    </div>
  </footer>
</template>

<script setup>
if (typeof window !== 'undefined') {
  const el = document.getElementById('year');
  if (el) el.textContent = String(new Date().getFullYear());
}
</script>
