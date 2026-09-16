<template>
  <div id="top">
    <Navbar />
    <main>
      <Transition name="page" mode="out-in">
        <router-view />
      </Transition>
    </main>
    <Footer />
    <ChatWidget />
    <a href="#top" class="back-top" aria-label="Back to top"><i class="bi bi-arrow-up"></i></a>
  </div>
</template>

<script setup>
import { nextTick, onBeforeUnmount, onMounted } from 'vue'
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
import ChatWidget from './components/ChatWidget.vue'

let observer
let mutationObserver

function prepareReveals() {
  const targets = document.querySelectorAll('main .section, main .hero-copy-block, main .hero-product-visual, main .cta-hero, main .product-page-hero, main .about-hero, main .how-hero, main .demo-hero, main .resource-feature, .footer-cta, .footer-grid, .footer-bottom')
  targets.forEach((el) => {
    if (!el.classList.contains('reveal-on-scroll')) el.classList.add('reveal-on-scroll')
    observer?.observe(el)
  })
}

onMounted(async () => {
  observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible')
        observer.unobserve(entry.target)
      }
    })
  }, { threshold: 0.08, rootMargin: '0px 0px -45px 0px' })

  await nextTick()
  prepareReveals()
  mutationObserver = new MutationObserver(() => prepareReveals())
  mutationObserver.observe(document.querySelector('main'), { childList: true, subtree: true })
})

onBeforeUnmount(() => {
  observer?.disconnect()
  mutationObserver?.disconnect()
})
</script>
