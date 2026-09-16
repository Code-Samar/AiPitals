<template>
  <div class="solution-page" :class="isClinic?'clinic-solution':'diagnostic-solution'">
    <section class="solution-hero">
      <div class="container">
        <div>
          <span class="eyebrow-pill">{{isClinic?'AIPITALS FOR CLINICS':'AIPITALS FOR DIAGNOSTIC CENTRES'}}</span>
          <h1 v-if="isClinic">Turn every patient interaction into a <span>better experience.</span></h1>
          <h1 v-else>Smarter patient journey. <span>Efficient lab operations.</span></h1>
          <p v-if="isClinic">Aipitals automates the repetitive work around patient enquiries, appointments, reminders, follow-ups and experience—so your team can focus on the people in front of them.</p>
          <p v-else>Aipitals connects with your existing LIS/CRM systems to automate the journey from enquiry to report delivery and follow-up—so your team can focus on accuracy, quality and care.</p>
          <div class="hero-actions"><RouterLink class="btn btn-primary rounded-pill" to="/contact">Book a Demo <i class="bi bi-arrow-right"></i></RouterLink><RouterLink class="btn btn-outline-primary rounded-pill" to="/how-it-works">See How It Works <i class="bi bi-arrow-right"></i></RouterLink></div>
        </div>
        <div class="solution-orbit">
          <div class="orbit-center"><img src="/assets/aipitals-mark.svg" alt="Aipitals"></div>
          <span v-for="x in orbit" :key="x.t" class="orbit-chip" :class="x.c"><i :class="x.i"></i> {{x.t}}</span>
        </div>
      </div>
    </section>

    <section class="long-section soft-bg">
      <div class="container">
        <div class="solution-challenge"><div><span class="eyebrow-pill">{{isClinic?'THE EVERYDAY WORK':'THE DAILY CHALLENGE'}}</span><h2>{{isClinic?'Your team shouldn’t have to chase every patient conversation.':'Too many patient queries. Too much manual work.'}}</h2><p>{{isClinic?'Enquiries, bookings, reminders, follow-ups and feedback can all be coordinated through one intelligent layer.':'Your staff spends hours every day on repetitive communication instead of focused diagnostic work.'}}</p></div><RouterLink class="btn btn-primary rounded-pill" to="/contact">{{isClinic?'Automate My Clinic':'Automate My Centre'}} <i class="bi bi-arrow-right"></i></RouterLink></div>
      </div>
    </section>

    <section class="long-section">
      <div class="container">
        <div class="long-heading"><span class="eyebrow-pill">{{isClinic?'THE CLINIC PATIENT JOURNEY':'THE DIAGNOSTIC PATIENT JOURNEY'}}</span><h2>{{isClinic?'One patient journey. Multiple opportunities to help.':'One journey. Fully automated with Aipitals.'}}</h2><p>Aipitals keeps every step connected and visible.</p></div>
        <div class="solution-journey"><div class="journey-box" v-for="x in journey" :key="x.t"><i :class="x.i"></i><b>{{x.t}}</b><small>{{x.p}}</small></div></div>
      </div>
    </section>

    <section class="long-section soft-bg">
      <div class="container"><div class="long-heading"><span class="eyebrow-pill">WHAT AIPITALS AUTOMATES</span><h2>{{isClinic?'Your front desk, without the repetitive work.':'End-to-end communication and coordination.'}}</h2></div><div class="solution-feature-grid"><div class="info-card" v-for="x in features" :key="x.t"><i :class="x.i"></i><h3>{{x.t}}</h3><p>{{x.p}}</p></div></div></div>
    </section>

    <section class="long-section">
      <div class="container"><div class="solution-system"><div><span class="eyebrow-pill">{{isClinic?'SEE IT IN ACTION':'BUILT TO INTEGRATE'}}</span><h2>{{isClinic?'From patient message to completed appointment.':'Works with your existing systems.'}}</h2><p class="text-muted">{{isClinic?'Aipitals coordinates the booking, reminders, visit and follow-up workflow without adding more manual work.':'Aipitals connects with LIS, CRM, billing and other systems. We enhance your workflow—we do not replace it.'}}</p></div><div class="system-flow"><span v-for="x in systems" :key="x"><i :class="x.i"></i>{{x.t}}</span></div></div></div>
    </section>

    <section class="long-section soft-bg">
      <div class="container"><div class="control-panel"><div class="control-copy"><span class="eyebrow-pill">AI WHEN IT MAKES SENSE. HUMAN WHEN IT MATTERS.</span><h2>AI handles the repetitive. <span>Humans handle what matters.</span></h2><p>Aipitals works within configured workflows and rules. When human attention is needed, conversations are routed to the right team member.</p></div><div class="control-list"><span><i class="bi bi-check-circle-fill"></i>Approved workflows</span><span><i class="bi bi-person-check"></i>Human escalation</span><span><i class="bi bi-shield-check"></i>Secure access</span><span><i class="bi bi-slash-circle"></i>No clinical decisions</span></div></div></div>
    </section>

    <section class="long-section"><div class="container"><div class="long-heading"><span class="eyebrow-pill">BENEFITS</span><h2>{{isClinic?'Less repetitive work. More time for patients.':'Better operations. Happier patients.'}}</h2></div><div class="problem-cards"><div class="info-card" v-for="x in benefits" :key="x.t"><i :class="x.i"></i><h3>{{x.t}}</h3><p>{{x.p}}</p></div></div></div></section>
  </div>
</template>
<script setup>
import {computed} from 'vue';import {useRoute} from 'vue-router'
const route=useRoute();const isClinic=computed(()=>route.params.type==='clinics')
const clinicJourney=[['Enquire','Patients reach out.','bi bi-chat-dots'],['Book','Appointments confirmed.','bi bi-calendar-check'],['Prepare','Instructions shared.','bi bi-clipboard-check'],['Visit','Better experience.','bi bi-person-check'],['Follow-up','Automated reminders.','bi bi-bell'],['Return','Bring patients back.','bi bi-arrow-repeat']]
const diagnosticJourney=[['Enquire','Test enquiries.','bi bi-chat-dots'],['Book','Appointment confirmed.','bi bi-calendar-check'],['Prepare','Test preparation.','bi bi-clipboard-check'],['Collect','Sample collected.','bi bi-droplet'],['Process','Testing in the lab.','bi bi-microscope'],['Report','Report delivered.','bi bi-file-earmark-text'],['Recall','Repeat care.','bi bi-arrow-repeat']]
const journey=computed(()=> (isClinic.value?clinicJourney:diagnosticJourney).map(x=>({t:x[0],p:x[1],i:x[2]})))
const clinicFeatures=[['Patient Enquiries','Answer routine questions instantly.','bi bi-chat-dots'],['Appointments','Book, confirm and reschedule automatically.','bi bi-calendar-check'],['Reminders','Reduce no-shows with timely reminders.','bi bi-bell'],['Follow-ups','Reconnect with patients after visits.','bi bi-arrow-repeat'],['Patient Experience','Collect feedback before issues escalate.','bi bi-heart'],['Human Handoff','Route complex conversations to staff.','bi bi-headset']]
const diagnosticFeatures=[['Patient Enquiries','Instant answers on tests, prices, timing and more.','bi bi-chat-dots'],['Bookings & Rescheduling','Book, confirm or reschedule appointments.','bi bi-calendar-check'],['Preparation Instructions','Send test-specific instructions and reminders.','bi bi-clipboard-check'],['Report Updates','Notify patients when reports are ready.','bi bi-file-earmark-text'],['Recall & Follow-ups','Bring patients back for repeat tests.','bi bi-arrow-repeat'],['Feedback & Experience','Collect feedback and improve patient satisfaction.','bi bi-star']]
const features=computed(()=> (isClinic.value?clinicFeatures:diagnosticFeatures).map(x=>({t:x[0],p:x[1],i:x[2]})))
const systems=computed(()=>isClinic.value?[{t:'Practice Management',i:'bi bi-calendar2-check'},{t:'EHR / EMR',i:'bi bi-heart-pulse'},{t:'Scheduling Systems',i:'bi bi-clock'},{t:'CRM',i:'bi bi-people'},{t:'Analytics & Reporting',i:'bi bi-bar-chart'}]:[{t:'LIS',i:'bi bi-flask'},{t:'CRM / Patient Database',i:'bi bi-people'},{t:'Billing System',i:'bi bi-receipt'},{t:'PMS / Scheduling',i:'bi bi-calendar2-check'},{t:'Analytics & Reporting',i:'bi bi-bar-chart'}])
const benefits=computed(()=>isClinic.value?[['Fewer missed enquiries','Never miss a patient opportunity.','bi bi-telephone'],['Less administrative work','Automate hours of repetitive communication.','bi bi-clock'],['Better follow-up','Patients return for the care they need.','bi bi-arrow-repeat'],['Better patient experience','Fast, consistent and helpful communication.','bi bi-heart']]:[['Fewer missed enquiries','Never miss a potential patient.','bi bi-telephone'],['Reduced staff workload','Save hours of repetitive communication.','bi bi-clock'],['Faster report delivery','Patients get timely updates and secure access.','bi bi-lightning-charge'],['Better experience','Consistent communication builds trust.','bi bi-star']].map(x=>({t:x[0],p:x[1],i:x[2]})))
const orbit=computed(()=>[{t:'Enquire',i:'bi bi-chat-dots',c:'one'},{t:'Book',i:'bi bi-calendar-check',c:'two'},{t:'Reminder',i:'bi bi-bell',c:'three'},{t:'Follow-up',i:'bi bi-arrow-repeat',c:'four'},{t:isClinic.value?'Consultation':'Report',i:'bi bi-file-earmark-text',c:'five'}])
</script>
