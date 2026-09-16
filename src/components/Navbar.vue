<template>
  <header class="site-nav redesign-nav">
    <nav class="navbar navbar-expand-xl">
      <div class="container nav-inner">
        <RouterLink class="brand-lockup" to="/" @click="closeMenu">
          <img src="/assets/aipitals-mark.svg" alt="Aipitals" />
          <strong>AIPITALS</strong>
        </RouterLink>
        <button class="navbar-toggler" type="button" @click="open=!open" :aria-expanded="open" aria-label="Toggle navigation">
          <i class="bi" :class="open ? 'bi-x-lg' : 'bi-list'"></i>
        </button>
        <div class="nav-panel redesign-panel" :class="{open}">
          <ul class="navbar-nav mx-auto align-items-xl-center">
            <li class="nav-item dropdown-wrap">
              <button class="nav-link nav-button" :class="{active: productsOpen}" @click.stop="toggleDropdown('products')" :aria-expanded="productsOpen">Products <i class="bi bi-chevron-down"></i></button>
              <Transition name="dropdown">
                <div v-if="productsOpen" class="nav-dropdown mega-dark products-menu">
                  <div class="menu-kicker">PRODUCTS</div>
                  <div class="mega-grid">
                    <div>
                      <div class="menu-group-title">PATIENT COMMUNICATION</div>
                      <RouterLink to="/products/whatsapp-ai-receptionist" @click="closeMenu"><b>WhatsApp AI Receptionist</b><small>Handle enquiries & appointments</small></RouterLink>
                      <RouterLink to="/products/patient-recall-agent" @click="closeMenu"><b>Patient Recall</b><small>Automate reminders & follow-ups</small></RouterLink>
                      <div class="menu-group-title second">PATIENT EXPERIENCE</div>
                      <RouterLink to="/products/patient-experience-reviews" @click="closeMenu"><b>Patient Experience</b><small>Feedback, recovery & reviews</small></RouterLink>
                    </div>
                    <div>
                      <div class="menu-group-title">DIAGNOSTICS</div>
                      <RouterLink to="/products/diagnostic-patient-os" @click="closeMenu"><b>Diagnostic Patient OS</b><small>Booking to report delivery</small></RouterLink>
                      <RouterLink to="/products/diagnostic-preparation-agent" @click="closeMenu"><b>Diagnostic Preparation</b><small>Automated test preparation</small></RouterLink>
                    </div>
                  </div>
                  <RouterLink class="dropdown-all" to="/products" @click="closeMenu">View all products <i class="bi bi-arrow-right"></i></RouterLink>
                </div>
              </Transition>
            </li>
            <li class="nav-item dropdown-wrap">
              <button class="nav-link nav-button" :class="{active: solutionsOpen}" @click.stop="toggleDropdown('solutions')" :aria-expanded="solutionsOpen">Solutions <i class="bi bi-chevron-down"></i></button>
              <Transition name="dropdown">
                <div v-if="solutionsOpen" class="nav-dropdown mega-dark solutions-menu">
                  <div class="menu-kicker">SOLUTIONS</div>
                  <RouterLink to="/solutions/clinics" @click="closeMenu"><b>FOR CLINICS</b><small>AI-powered patient operations<br>Enquiries · appointments · follow-ups</small><em>Explore Clinic Solutions →</em></RouterLink>
                  <RouterLink to="/solutions/diagnostic-centres" @click="closeMenu"><b>FOR DIAGNOSTIC CENTRES</b><small>End-to-end diagnostic patient operations<br>Booking · preparation · reports · follow-ups</small><em>Explore Diagnostic Solutions →</em></RouterLink>
                </div>
              </Transition>
            </li>
            <li><RouterLink class="nav-link" to="/resources" @click="closeMenu">Resources</RouterLink></li>
            <li class="nav-item dropdown-wrap">
              <button class="nav-link nav-button" :class="{active: companyOpen}" @click.stop="toggleDropdown('company')" :aria-expanded="companyOpen">Company <i class="bi bi-chevron-down"></i></button>
              <Transition name="dropdown">
                <div v-if="companyOpen" class="nav-dropdown company-menu">
                  <RouterLink to="/about" @click="closeMenu"><b>About Aipitals</b><small>Our mission and approach</small></RouterLink>
                  <RouterLink to="/faq" @click="closeMenu"><b>FAQ</b><small>Common questions answered</small></RouterLink>
                  <RouterLink to="/contact" @click="closeMenu"><b>Contact Us</b><small>Talk to our team</small></RouterLink>
                </div>
              </Transition>
            </li>
          </ul>
          <div class="nav-actions">
            <RouterLink class="btn btn-primary rounded-pill px-4" to="/contact" @click="closeMenu"><i class="bi bi-calendar2 me-1"></i> Book a Demo</RouterLink>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>
<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'
const open=ref(false),productsOpen=ref(false),solutionsOpen=ref(false),companyOpen=ref(false)
function toggleDropdown(name){productsOpen.value=name==='products'?!productsOpen.value:false;solutionsOpen.value=name==='solutions'?!solutionsOpen.value:false;companyOpen.value=name==='company'?!companyOpen.value:false}
function closeDropdowns(){productsOpen.value=false;solutionsOpen.value=false;companyOpen.value=false}
function closeMenu(){open.value=false;closeDropdowns()}
function handleDocumentClick(){closeDropdowns()}
function handleEscape(e){if(e.key==='Escape')closeMenu()}
onMounted(()=>{document.addEventListener('click',handleDocumentClick);document.addEventListener('keydown',handleEscape)})
onBeforeUnmount(()=>{document.removeEventListener('click',handleDocumentClick);document.removeEventListener('keydown',handleEscape)})
</script>
