# Partner Enquiry

> Partner enquiry for EOR and payroll platforms that need an in-country employer in Italy.


<section> <span class="eyebrow">Partner enquiry</span> <h1 id="tell-us-about-your-platform">Tell us about your platform</h1> <p class="lede">Three short steps. We reply within one business day with sample outputs and a partner rate.</p> </section> <section> <form id="lead" class="panel" style="display:grid;gap:18px;max-width:640px" novalidate> <p id="stepinfo" class="tag" style="justify-self:start">Step 1 of 3</p> <fieldset data-step="1" style="border:0;padding:0;margin:0;display:grid;gap:14px"> <label for="email">Work email<input id="email" type="email" autocomplete="email" required></label> <label for="company">Company<input id="company" autocomplete="organization"></label> </fieldset> <fieldset data-step="2" hidden style="border:0;padding:0;margin:0;display:grid;gap:14px"> <label for="service">Platform type<select id="service"><option>Global EOR</option><option>Global payroll</option><option>EOR and payroll</option><option>Mobility / visas</option></select></label> <label for="count">Employees in Italy today<input id="count" type="number" min="0" value="0"></label> <label for="forecast">Expected employees in Italy in 12 months<input id="forecast" type="number" min="0"></label> <label for="integration">Preferred data exchange<select id="integration"><option>REST API</option><option>SFTP file (CSV/JSON)</option><option>Not decided</option></select></label> </fieldset> <fieldset data-step="3" hidden style="border:0;padding:0;margin:0;display:grid;gap:14px"> <label for="name">Your name<input id="name" autocomplete="name"></label> <label for="role">Your role<input id="role" placeholder="Ops, partnerships, payroll…"></label> <label for="notes">Anything else<textarea id="notes" rows="4"></textarea></label> <label style="display:flex;gap:10px;align-items:flex-start;font-weight:400"><input id="consent" type="checkbox" style="width:auto;margin-top:5px">I agree that ItalyInCountry processes my data to answer this request (privacy policy).</label> </fieldset> <p id="msg" role="status" style="margin:0;color:var(--accent)"></p> <div class="cta"><button type="button" class="btn ghost" id="back" hidden>Back</button><button type="submit" class="btn" id="next">Continue</button></div> </form> </section> <script>
// Il passo 1 salva subito l'email (lead abbandonato recuperabile dal nurturing). Endpoint del worker: /api/lead.
const f = document.getElementById('lead'); let step = 1;
const sets = [...f.querySelectorAll('fieldset')];
const data = () => Object.fromEntries([...f.querySelectorAll('input,select,textarea')].map(e => [e.id, e.type === 'checkbox' ? e.checked : e.value]));
async function save(final){ try { await fetch('/api/lead', {method:'POST', headers:{'Content-Type':'application/json'}, body: JSON.stringify({...data(), step, final, brand:'italyincountry'})}); } catch(e){} }
function show(){ sets.forEach(s => s.hidden = +s.dataset.step !== step);
  document.getElementById('stepinfo').textContent = `Step ${step} of 3`;
  document.getElementById('back').hidden = step === 1;
  document.getElementById('next').textContent = step === 3 ? 'Send request' : 'Continue'; }
// Ripresa dal link nelle email: ?resume=<token> precompila i campi e salta al passo successivo.
(async () => { const tok = new URLSearchParams(location.search).get('resume'); if (!tok) return;
  try { const r = await fetch('/api/lead/' + encodeURIComponent(tok)); if (!r.ok) return; const d = await r.json();
    for (const [k, v] of Object.entries(d)) { const el = document.getElementById(k); if (el && v != null) el.value = v; }
    step = d.step || 2; show(); } catch(e){} })();
document.getElementById('back').onclick = () => { step--; show(); };
f.addEventListener('submit', e => { e.preventDefault(); const m = document.getElementById('msg'); m.textContent = '';
  if (step === 1 && !document.getElementById('email').checkValidity()) { m.textContent = 'Enter a valid work email to continue.'; return; }
  if (step === 3 && !document.getElementById('consent').checked) { m.textContent = 'Tick the consent box so we can reply.'; return; }
  save(step === 3);
  if (step < 3) { step++; show(); } else { f.querySelectorAll('fieldset,.cta').forEach(x => x.hidden = true); m.textContent = 'Thank you. We will reply within one business day.'; } });
</script>

<script>(function(){var sj=new URLSearchParams(location.search).get('subject');var n=document.getElementById('notes');if(sj&&n&&!n.value)n.value='['+sj.slice(0,40)+'] ';})();</script>


---
Source: https://italyincountry.com/contact.html
