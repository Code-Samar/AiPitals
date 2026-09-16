<template>
<div class="home-redesign">
<section class="hero-modern redesign-hero">
  <div class="container">
    <div class="hero-grid redesign-hero-grid">
      <div class="hero-copy-block">
        <span class="eyebrow-pill">AI PATIENT OPERATIONS</span>
        <h1>Automate the work<br>between every<br><span>patient interaction.</span></h1>
        <p>Aipitals gives clinics and diagnostic centres AI systems that handle enquiries, appointments, reminders, diagnostics and follow-ups—while your team stays in control.</p>
        <div class="hero-actions">
          <RouterLink class="btn btn-primary btn-lg rounded-pill px-4" to="/contact">Book a Demo <i class="bi bi-arrow-right"></i></RouterLink>
          <RouterLink class="btn btn-outline-primary btn-lg rounded-pill px-4" to="/how-it-works">See Aipitals in Action <i class="bi bi-arrow-right"></i></RouterLink>
        </div>
        <div class="hero-trust-row"><span><i class="bi bi-shield-check"></i> Human handoff when needed</span><span><i class="bi bi-check2-circle"></i> Built for healthcare workflows</span><span><i class="bi bi-clock"></i> Available 24/7</span></div>
      </div>
      <div class="hero-product-visual">
        <div class="hero-tabs"><span class="active"><i class="bi bi-chat-dots"></i> AI Receptionist</span><span><i class="bi bi-bell"></i> Patient Recall</span><span><i class="bi bi-diagram-3"></i> Diagnostics</span></div>
        <div class="hero-dashboard">
          <div class="hero-chat-card">
            <div class="mock-head"><span class="status-dot"></span><b>Aipitals AI Receptionist</b><small>Online</small></div>
            <div class="mock-chat">
              <div class="mock-bubble patient">Hi, I want to book an appointment with Dr. Sharma.</div>
              <div class="mock-bubble ai">Sure! Please choose a preferred date.</div>
              <div class="mock-bubble patient">Tomorrow, 10:30 AM</div>
              <div class="mock-bubble ai">Your appointment is confirmed. <i class="bi bi-check-circle-fill"></i></div>
            </div>
            <div class="mock-input">Type a message... <i class="bi bi-send-fill"></i></div>
          </div>
          <div class="hero-workflow-card">
            <div class="workflow-title">AUTOMATED PATIENT WORKFLOWS</div>
            <div v-for="x in workflow" :key="x.t" class="workflow-row"><span class="workflow-icon" :class="x.c"><i :class="x.i"></i></span><div><b>{{x.t}}</b><small>{{x.p}}</small></div><i class="bi bi-check-circle-fill done"></i></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="stats-band"><div class="container"><div class="stats-label">TRUSTED BY CLINICS & DIAGNOSTIC CENTRES</div><div class="stats-grid"><div v-for="s in stats" :key="s.n"><i :class="s.i"></i><strong>{{s.n}}</strong><span>{{s.t}}</span></div></div></div></section>

<section class="section problem-section"><div class="container"><div class="section-heading center"><span class="eyebrow-pill">THE EVERYDAY WORK</span><h2>Too many patient conversations.<br><span>Not enough time.</span></h2><p>Your team spends hours on repetitive communication instead of patient care.</p></div>
  <div class="problem-board">
    <div class="problem-column pink"><h4>LEFT UNHANDLED</h4><b>Disorganised. Overwhelming.</b><div v-for="x in leftWork" :key="x.t" class="problem-row"><i :class="x.i"></i><div><b>{{x.t}}</b><small>{{x.p}}</small></div><span>{{x.time}}</span></div><footer><i class="bi bi-person-x"></i> Staff busy with repetitive work</footer></div>
    <div class="problem-core"><span class="flow-beam flow-beam-left" aria-hidden="true"></span><span>AIPITALS AI</span><div class="core-logo"><img src="/assets/aipitals-mark.svg" alt="Aipitals"></div><b>Handles the work</b><small>Always-on · 24/7</small><span class="flow-beam flow-beam-right" aria-hidden="true"></span></div>
    <div class="problem-column green"><h4>HANDLED AUTOMATICALLY</h4><b>Keep opportunities moving.</b><div v-for="x in rightWork" :key="x.t" class="problem-row"><i :class="x.i"></i><div><b>{{x.t}}</b><small>{{x.p}}</small></div><span><i class="bi bi-check-circle-fill"></i></span></div><footer><i class="bi bi-person-check"></i> Team focuses on patient care</footer></div>
    <div class="problem-bottom"><span><i class="bi bi-clock"></i> Saves hours every single day</span><span><i class="bi bi-calendar-check"></i> Never misses calls & appointments</span><span><i class="bi bi-graph-up-arrow"></i> More patients served every day</span><span><i class="bi bi-heart"></i> Better patient experience</span></div>
  </div>
</div></section>

<section class="section products-preview redesigned-products"><div class="container"><div class="section-heading center"><span class="eyebrow-pill">OUR AI PRODUCTS</span><h2>Aipitals gives clinics and diagnostic centres<br>specialized AI systems for <span>patient communication,<br>diagnostics, follow-ups and patient experience.</span></h2></div>
  <div class="product-strip">
    <RouterLink v-for="(p,i) in products" :key="p.slug" :to="'/products/'+p.slug" class="product-mini redesign-product-card">
      <div class="product-card-head"><div class="mini-icon" :class="'c'+i"><i :class="['bi',p.icon]"></i></div><span>0{{i+1}}</span></div><h3>{{shortNames[i]}}</h3><p>{{cardCopy[i]}}</p><div class="mini-demo" :class="'demo-'+i"><template v-if="i===0"><span>Hi, I want to book an appointment</span><span>Sure! Please choose a date.</span></template><template v-else-if="i===1"><span><i class="bi bi-check-circle-fill"></i> Follow-up due</span><span><i class="bi bi-clock"></i> Reminder scheduled</span></template><template v-else-if="i===2"><span>Booked</span><span>Sample collected</span><span>Report delivered</span></template><template v-else-if="i===3"><span>Fasting required</span><span>Preparation confirmed</span></template><template v-else><span>How was your experience?</span><span class="stars">★★★★★</span></template></div><span class="explore-link">Explore <i class="bi bi-arrow-right"></i></span>
    </RouterLink>
  </div>
  <div class="center-link"><RouterLink class="btn btn-outline-primary rounded-pill px-4" to="/products">View all products <i class="bi bi-arrow-right"></i></RouterLink></div>
</div></section>

<section class="section journey-section"><div class="container"><div class="section-heading center"><span class="eyebrow-pill">THE PATIENT JOURNEY</span><h2>From enquire to return.<br>We’re with your patients <span>at every step.</span></h2><p>Aipitals AI works across the entire patient journey.</p></div><div class="journey-flow"><div v-for="(s,i) in journey" :key="s.t" class="journey-node"><span class="journey-number">0{{i+1}}</span><div class="journey-icon"><i :class="s.i"></i></div><b>{{s.t}}</b><small>{{s.p}}</small><em v-if="i<5"><i class="bi bi-arrow-right"></i></em></div></div><div class="journey-note"><i class="bi bi-stars"></i> One intelligent layer. Every interaction. Better experience for patients. Less work for your team.</div></div></section>

<section class="section responsible-section"><div class="container"><div class="responsible-top"><div><span class="eyebrow-pill"><i class="bi bi-shield-check"></i> RESPONSIBLE AI</span><h2>AI when it makes sense.<br><span>Humans when it matters.</span></h2><p>Aipitals AI handles repetitive communication and admin tasks, so your team can focus on what truly matters—patient care.</p><RouterLink class="arrow-link" to="/how-it-works">Learn more about our approach to responsible AI <i class="bi bi-arrow-right"></i></RouterLink></div><div class="responsible-flow"><div class="flow-source"><span v-for="x in sourceTasks" :key="x.t"><i :class="x.i"></i>{{x.t}}</span></div><div class="flow-core"><span>AIPITALS AI</span><div><img src="/assets/aipitals-mark.svg" alt="Aipitals"></div><small>Understands. Responds.<br>Acts intelligently.</small></div><div class="flow-results"><span v-for="x in resultTasks" :key="x"><i class="bi bi-check-circle-fill"></i>{{x}}</span></div></div></div><div class="responsible-values"><div v-for="x in responsible" :key="x.t"><i :class="x.i"></i><b>{{x.t}}</b><p>{{x.p}}</p></div></div></div></section>

<section class="section cta-section"><div class="container"><div class="cta-hero"><div class="cta-copy"><span class="eyebrow-pill">✦ READY TO GET STARTED?</span><h2>Ready to automate<br>your <span>patient operations?</span></h2><p>See how Aipitals AI can save your team hours every day, improve patient experience, and grow your clinic.</p><div class="hero-actions"><RouterLink class="btn btn-primary btn-lg rounded-pill px-4" to="/contact">Book a Demo <i class="bi bi-arrow-right"></i></RouterLink><RouterLink class="btn btn-outline-light btn-lg rounded-pill px-4" to="/how-it-works"><i class="bi bi-play-circle"></i> See Aipitals in Action</RouterLink></div><div class="cta-checks"><span>✓ Personalized Demo</span><span>✓ No Commitment</span><span>✓ Takes 15 Minutes</span></div></div><div class="cta-visual"><div class="mini-dashboard"><b>Aipitals Dashboard</b><div class="dash-stats"><span><b>128</b>Appointments</span><span><b>96</b>Follow-ups</span><span><b>320</b>Patient Engaged</span></div><div class="dash-line"></div><div class="dash-list"><span><i class="bi bi-calendar-check"></i> New Appointment Booked</span><span><i class="bi bi-bell"></i> Reminder Sent</span><span><i class="bi bi-arrow-repeat"></i> Follow-up Completed</span></div></div><img src="/assets/doctor-hero.jpg" alt="Healthcare professional using Aipitals"></div></div></div></section>
</div>
</template>
<script setup>
import {products} from '../data/products'
const workflow=[{t:'Appointment Booked',p:'Confirmed with patient',i:'bi bi-calendar-check',c:'blue'},{t:'Reminder Sent',p:'Via WhatsApp & SMS',i:'bi bi-bell',c:'purple'},{t:'Follow-up Scheduled',p:'Post-visit workflow',i:'bi bi-person-check',c:'green'},{t:'Experience & Review',p:'Collect feedback',i:'bi bi-star',c:'orange'}]
const stats=[{n:'10,000+',t:'Patient conversations handled every day',i:'bi bi-chat-dots'},{n:'300+',t:'Clinics & labs trust Aipitals',i:'bi bi-building-check'},{n:'40%+',t:'Reduction in missed opportunities',i:'bi bi-graph-down-arrow'},{n:'2M+',t:'Appointments & follow-ups automated',i:'bi bi-calendar2-check'}]
const leftWork=[{t:'Missed Call',p:'+91 98765 43210',time:'10:32 AM',i:'bi bi-telephone'},{t:'Appointment Request',p:'Dr. Sharma · New enquiry',time:'10:35 AM',i:'bi bi-calendar-plus'},{t:'Reschedule Request',p:'Patient wants new slot',time:'10:42 AM',i:'bi bi-arrow-repeat'},{t:'Reminder Pending',p:'12 appointments today',time:'10:50 AM',i:'bi bi-bell'}]
const rightWork=[{t:'Appointment Booked',p:'Dr. Sharma · 10:30 AM',i:'bi bi-calendar-check'},{t:'Call Answered',p:'Appointment information shared',i:'bi bi-telephone'},{t:'Appointment Rescheduled',p:'New slot confirmed',i:'bi bi-arrow-repeat'},{t:'Reminder Sent',p:'12 reminders sent successfully',i:'bi bi-bell'}]
const shortNames=['WhatsApp AI Receptionist','Patient Recall','Diagnostic Patient OS','Diagnostic Preparation','Patient Experience']
const cardCopy=['AI-powered patient enquiries & appointments.','Automated reminders & follow-ups.','One intelligent workflow from booking to report delivery.','Automated test preparation & instructions.','Post-consultation feedback & reviews.']
const journey=[{t:'Enquire',p:'Patients reach out on WhatsApp, app, call or chat.',i:'bi bi-chat-dots'},{t:'Book',p:'AI books appointments, manages availability and confirms instantly.',i:'bi bi-calendar-check'},{t:'Prepare',p:'We share instructions and help patients prepare for tests.',i:'bi bi-clipboard-check'},{t:'Visit / Test',p:'Smooth check-in and test / consultation experience.',i:'bi bi-stethoscope'},{t:'Follow Up',p:'Reports, reminders and follow-ups are automated.',i:'bi bi-bell'},{t:'Return',p:'We bring patients back for the next visit or test.',i:'bi bi-arrow-repeat'}]
const sourceTasks=[{t:'WhatsApp',i:'bi bi-whatsapp'},{t:'Phone Call',i:'bi bi-telephone'},{t:'Appointment',i:'bi bi-calendar-check'},{t:'Reminder',i:'bi bi-bell'}]
const resultTasks=['Appointment Booked','Information Shared','Reminder Sent','Follow-up Scheduled']
const responsible=[{t:'Human Handoff',p:'When a conversation needs human judgment, Aipitals instantly transfers it to your team.',i:'bi bi-person-check'},{t:'Approved Workflows',p:'Every response follows your clinic’s approved workflows, templates and communication rules.',i:'bi bi-shield-check'},{t:'Data Security',p:'Your data is encrypted, stored securely and never shared. Privacy by design.',i:'bi bi-lock'},{t:'No Clinical Decisions',p:'Aipitals AI does not diagnose, prescribe or replace doctors in any way.',i:'bi bi-slash-circle'}]
</script>
