<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const interest = ref('')

const submitting = ref(false)
const msgText = ref('')             // isi pesan
const msgType = ref('')             // 'success' | 'error'

function resetMsg(){ msgText.value=''; msgType.value='' }

function validate(){
  let ok = true
  if(!name.value) ok = false
  if(!email.value) ok = false
  else {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
    if(!re.test(email.value)) ok = false
  }
  if(!interest.value) ok = false
  console.log('[CTA] validate ->', ok, { name: name.value, email: email.value, interest: interest.value })
  return ok
}

async function onSubmit(e){
  e.preventDefault()
  resetMsg()
  console.log('[CTA] submit', { name: name.value, email: email.value, interest: interest.value })

  if(!validate()){
    msgType.value = 'error'
    msgText.value = 'Please complete the form.'
    return
  }

  try{
    submitting.value = true

    // ====== GANTI endpoint di bawah ini ke API kamu ======
    const res = await fetch('/api/early-access', {
      method:'POST',
      headers:{ 'Content-Type':'application/json' },
      body: JSON.stringify({ name: name.value, email: email.value, interest: interest.value })
    })

    console.log('[CTA] response status', res.status)
    let data = null
    try { data = await res.json() } catch(_) {}
    console.log('[CTA] response json', data)

    if(!res.ok){
      const backendMsg = data?.message || data?.error
      throw new Error(backendMsg || `Failed to submit (code ${res.status})`)
    }

    msgType.value = 'success'
    msgText.value = 'Thanks! You’re on the list 🎉'
    name.value = ''
    email.value = ''
    interest.value = ''

  }catch(err){
    console.error('[CTA] error', err)
    msgType.value = 'error'
    msgText.value = err?.message || 'Network error. Please try again.'
  }finally{
    submitting.value = false
  }
}
</script>

<template>
  <section id="early" class="cta-section">
    <div class="container">
      <h2 class="title" style="font-size:36px;color:#e5e7eb;text-align:center;margin-bottom:8px">
        Be Part of the First Wave
      </h2>
      <p class="muted" style="text-align:center;margin:0 0 22px;color:#a8b3c7">
        Help shape the future of Konnetto by joining our early access program
      </p>

      <div class="cta-box">
        <!-- FORM: desain & markup sama persis -->
        <form class="form" @submit="onSubmit" novalidate>
          <input class="input" v-model.trim="name" placeholder="Your name" :disabled="submitting" required>
          <input class="input" v-model.trim="email" type="email" placeholder="Your email" :disabled="submitting" required>

          <select class="full" v-model="interest" aria-label="What interests you most?" :disabled="submitting">
            <option value="">What interests you most about Konnetto?</option>
            <option>Anime & Manga</option>
            <option>Cosplay</option>
            <option>VTubers</option>
            <option>Artists</option>
            <option>Conventions</option>
            <option>J-Music</option>
          </select>

          <button class="btn dark full" type="submit" :disabled="submitting">
            <span v-if="!submitting">Join Early Access <span class="arrow">→</span></span>
            <span v-else class="btn-spinner" aria-hidden="true"></span>
          </button>
        </form>

        <!-- Inline message kecil; tidak mengubah layout -->
        <div class="cta-inline-msg" :data-type="msgType" aria-live="polite">
          {{ msgText }}
        </div>

        <p class="legend">We’ll never share your information with third parties.</p>
      </div>

      <p style="text-align:center;margin-top:26px;color:#7b8aa2">
        Future home of our partners and supporters
      </p>
    </div>
  </section>
</template>

<style scoped>
/* menjaga desain: pesan kecil, tidak geser layout (reserve height) */
.cta-inline-msg{
  min-height: 20px;                 /* reserve ruang agar layout tetap */
  margin: 10px 2px 0;
  font-weight: 700;
  font-size: 14px;
  letter-spacing: .2px;
  opacity: .95;
}
.cta-inline-msg[data-type="success"]{ color:#d1fae5 }  /* hijau muda di dark bg */
.cta-inline-msg[data-type="error"]{ color:#fecaca }    /* merah muda di dark bg */

/* spinner kecil di tombol, tetap estetis */
.btn .btn-spinner{
  width:18px;height:18px;border-radius:999px;
  border:2px solid rgba(255,255,255,.55);border-top-color:#fff;
  animation:spin .7s linear infinite;display:inline-block;
}
@keyframes spin{ to{ transform:rotate(360deg) } }
</style>
