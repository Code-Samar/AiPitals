<template>
  <footer class="footer">
    <div class="container">
      <section class="footer-cta">
        <div class="footer-cta-copy">
          <span class="eyebrow">READY TO START?</span>
          <h2>Ready to transform your<br class="d-none d-md-block" /> patient operations?</h2>
          <p>Book a demo to see how Aipitals AI can fit into your clinic or diagnostic centre.</p>
        </div>
        <RouterLink class="footer-demo-btn" to="/contact">
          <span>Book a Demo</span><i class="bi bi-arrow-up-right"></i>
        </RouterLink>
      </section>

      <div class="footer-divider"></div>

      <div class="footer-grid">
        <div class="footer-brand-col">
          <RouterLink to="/" class="footer-logo">
            <img src="/assets/aipitals-mark.svg" alt="Aipitals" /><span>AIPITALS</span>
          </RouterLink>
          <p>AI Patient Operations for Clinics & Diagnostic Centres.</p>
          <div class="socials" aria-label="Social media">
            <span aria-label="LinkedIn"><i class="bi bi-linkedin"></i></span>
            <span aria-label="Instagram"><i class="bi bi-instagram"></i></span>
            <span aria-label="YouTube"><i class="bi bi-youtube"></i></span>
            <span aria-label="X"><i class="bi bi-twitter-x"></i></span>
          </div>
        </div>

        <div class="footer-links-col"><h6>Products</h6><RouterLink v-for="p in products" :key="p.slug" :to="'/products/'+p.slug">{{p.name}}</RouterLink></div>
        <div class="footer-links-col"><h6>Solutions</h6><RouterLink to="/solutions/clinics">For Clinics</RouterLink><RouterLink to="/solutions/diagnostic-centres">For Diagnostic Centres</RouterLink><RouterLink to="/how-it-works">How It Works</RouterLink></div>
        <div class="footer-links-col"><h6>Company</h6><RouterLink to="/about">About</RouterLink><RouterLink to="/resources">Resources</RouterLink><RouterLink to="/contact">Contact</RouterLink><RouterLink to="/faq">FAQ</RouterLink></div>
        <div class="footer-links-col"><h6>Legal</h6><RouterLink to="/privacy">Privacy</RouterLink><RouterLink to="/terms">Terms</RouterLink></div>
      </div>

      <div class="footer-bottom">
        <span>© {{year}} Aipitals. Built for the next generation of healthcare businesses.</span>
        <span class="footer-status"><i></i> AI systems, built responsibly</span>
      </div>
    </div>
  </footer>
</template>

<script setup>
import {products} from '../data/products'
const year=new Date().getFullYear()
</script>
