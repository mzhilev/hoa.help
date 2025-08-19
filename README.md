import React from "react";

// NOTE: This single-file React page is designed to drop into a Next.js or Create React App project.
// Styling uses Tailwind CSS. If Tailwind isn't set up yet, you can still reuse the JSX/content.
// Replace phone/email below before going live.

export default function HOAHelpSite() {
  return (
    <div className="min-h-screen bg-white text-slate-900 antialiased">
      <Header />
      <Hero />
      <TrustBar />
      <Promises />
      <Process />
      <Scorecard />
      <Features />
      <Comparison />
      <FAQ />
      <CTA />
      <Contact />
      <Footer />
      <StructuredData />
    </div>
  );
}

function Header() {
  return (
    <header className="sticky top-0 z-50 bg-white/80 backdrop-blur border-b border-slate-200">
      <div className="mx-auto max-w-7xl px-4 py-3 flex items-center justify-between">
        <a href="#top" className="flex items-center gap-3">
          <div className="h-9 w-9 rounded-2xl bg-slate-900 text-white grid place-items-center font-bold">H</div>
          <div className="leading-tight">
            <div className="text-xl font-black tracking-tight">HOA.help</div>
            <div className="text-xs text-slate-500 -mt-0.5">Always here to help</div>
          </div>
        </a>
        <nav className="hidden md:flex items-center gap-7 text-sm">
          <a className="hover:text-slate-900 text-slate-600" href="#promises">Promises</a>
          <a className="hover:text-slate-900 text-slate-600" href="#process">Onboarding</a>
          <a className="hover:text-slate-900 text-slate-600" href="#scorecard">Promised Land</a>
          <a className="hover:text-slate-900 text-slate-600" href="#features">Services</a>
          <a className="hover:text-slate-900 text-slate-600" href="#faq">FAQ</a>
        </nav>
        <div className="flex items-center gap-3">
          <a href="tel:+13125551234" className="hidden sm:inline-block rounded-2xl border px-4 py-2 text-sm hover:shadow">Call</a>
          <a href="sms:+13125551234" className="hidden sm:inline-block rounded-2xl border px-4 py-2 text-sm hover:shadow">Text</a>
          <a href="#contact" className="inline-block rounded-2xl bg-slate-900 text-white px-4 py-2 text-sm hover:opacity-90">Get Proposal</a>
        </div>
      </div>
    </header>
  );
}

function Hero() {
  return (
    <section className="relative overflow-hidden">
      <div className="absolute inset-0 -z-10 bg-[radial-gradient(60%_50%_at_70%_10%,#e2e8f0,transparent_60%)]"/>
      <div className="mx-auto max-w-7xl px-4 pt-16 pb-10 grid md:grid-cols-2 items-center gap-10">
        <div>
          <h1 className="text-4xl md:text-6xl font-black tracking-tight leading-[1.05]">
            Efficient HOA management that saves you time and ends surprise assessments.
          </h1>
          <p className="mt-4 text-lg text-slate-600 max-w-prose">
            We combine 24/7 support with disciplined financial controls so your community runs smoothly and builds healthy reserves—without special assessments.
          </p>
          <div className="mt-6 flex flex-wrap gap-3">
            <a href="#contact" className="rounded-2xl bg-slate-900 text-white px-5 py-3 font-semibold">Get a Proposal</a>
            <a href="#process" className="rounded-2xl border px-5 py-3 font-semibold">How it works</a>
            <a href="mailto:hello@hoa.help" className="rounded-2xl border px-5 py-3 font-semibold">Email Us</a>
          </div>
          <ul className="mt-6 text-sm text-slate-600 grid grid-cols-1 sm:grid-cols-2 gap-2">
            <li>• 15–30 min orientation call</li>
            <li>• 2‑week enrollment/onboarding</li>
            <li>• 3–6 month plan to strong budgets & reserves</li>
            <li>• Autopay + owner portal + real-time updates</li>
          </ul>
        </div>
        <div className="relative">
          <div className="rounded-3xl border bg-white p-4 shadow-sm">
            <div className="rounded-2xl bg-slate-50 p-4">
              <div className="text-xs uppercase tracking-wide text-slate-500">At a glance</div>
              <div className="mt-3 grid grid-cols-2 gap-4">
                {[
                  {k:"24/7", v:"Call · Text · Email"},
                  {k:">20%", v:"Annual reserves target"},
                  {k:"0", v:"Special assessments"},
                  {k:"2 weeks", v:"Enrollment time"},
                ].map((item,i)=> (
                  <div key={i} className="rounded-xl bg-white border p-4">
                    <div className="text-2xl font-black">{item.k}</div>
                    <div className="text-slate-600 text-sm">{item.v}</div>
                  </div>
                ))}
              </div>
            </div>
          </div>
          <p className="mt-4 text-xs text-slate-500">* Targets shown are goals; implementation depends on each HOA's starting point and bylaws.</p>
        </div>
      </div>
    </section>
  );
}

function TrustBar(){
  return (
    <section className="border-y bg-slate-50/60">
      <div className="mx-auto max-w-7xl px-4 py-6 grid grid-cols-2 md:grid-cols-4 gap-4 text-sm text-slate-600">
        <div><span className="font-semibold text-slate-900">Illinois‑focused</span><br/>Chicago & suburbs</div>
        <div><span className="font-semibold text-slate-900">Real‑time</span><br/>Google Drive financials</div>
        <div><span className="font-semibold text-slate-900">Autopay</span><br/>Buildium setup for owners</div>
        <div><span className="font-semibold text-slate-900">Transparent</span><br/>Quarterly board updates</div>
      </div>
    </section>
  );
}

function Promises(){
  return (
    <section id="promises" className="mx-auto max-w-7xl px-4 py-16">
      <h2 className="text-3xl md:text-4xl font-black tracking-tight">Our two core promises</h2>
      <div className="mt-6 grid md:grid-cols-2 gap-6">
        <Card title="Always here 24/7" desc="Call, text, or email any time—human replies with triage and follow‑through." bullets={["Live monitoring","Same‑day status updates","Emergency dispatch coordination"]} />
        <Card title="No surprise ‘specials’" desc="Disciplined budgeting so regular assessments cover operations and reserves." bullets={["Conservative budgets",">20% revenue to reserves","Monthly budget vs. actuals"]} />
      </div>
    </section>
  );
}

function Card({title, desc, bullets}:{title:string; desc:string; bullets:string[]}){
  return (
    <div className="rounded-3xl border p-6 bg-white shadow-sm">
      <h3 className="text-xl font-extrabold">{title}</h3>
      <p className="mt-2 text-slate-600">{desc}</p>
      <ul className="mt-4 space-y-2 text-sm text-slate-700">
        {bullets.map((b,i)=> <li key={i}>• {b}</li>)}
      </ul>
    </div>
  );
}

function Process(){
  const steps = [
    {t:"Orientation Call (15–30 min)", d:"Share budget/financials and current issues. We outline an on‑the‑spot action plan."},
    {t:"Two‑Week Enrollment", d:"On‑site scan, lockbox & utilities setup, vendor logins, owner contact list, Buildium owner import."},
    {t:"3–6 Month Execution", d:"Stabilize ops, enforce policies, implement autopay, automate bills, reserve contributions >20%."},
  ];
  return (
    <section id="process" className="mx-auto max-w-7xl px-4 py-16">
      <h2 className="text-3xl md:text-4xl font-black tracking-tight">A simple 3‑step plan</h2>
      <div className="mt-6 grid md:grid-cols-3 gap-6">
        {steps.map((s,i)=> (
          <div key={i} className="rounded-3xl border p-6 bg-white">
            <div className="h-10 w-10 rounded-full border grid place-items-center font-bold">{i+1}</div>
            <h3 className="mt-4 text-xl font-extrabold">{s.t}</h3>
            <p className="mt-2 text-slate-600">{s.d}</p>
          </div>
        ))}
      </div>
    </section>
  );
}

function Scorecard(){
  const items = [
    "All owners on Autopay through Buildium",
    "Single annual meeting + quarterly board updates",
    ">20% of revenue to reserves; zero special assessments",
    "Monthly financials to Google Drive (not inbox‑spam)",
    "Automated AP for utilities & regular vendors",
    "Clear rules, reminders, and fair enforcement",
    "24/7 response with instant triage",
  ];
  return (
    <section id="scorecard" className="mx-auto max-w-7xl px-4 py-16">
      <h2 className="text-3xl md:text-4xl font-black tracking-tight">Your “Promised Land” scorecard</h2>
      <p className="mt-2 text-slate-600 max-w-prose">Where we aim to land every HOA within 3–6 months. Track progress live and celebrate the wins.</p>
      <div className="mt-6 grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
        {items.map((x,i)=> (
          <label key={i} className="rounded-2xl border p-4 flex items-start gap-3 bg-white">
            <input type="checkbox" defaultChecked className="mt-1 h-5 w-5 rounded border-slate-300"/>
            <span className="text-sm">{x}</span>
          </label>
        ))}
      </div>
    </section>
  );
}

function Features(){
  const cols = [
    {h:"Financials", items:["Budget & reserves planning","Monthly budget vs. actuals","AP/AR, collections, late fees","Tax filings & bookkeeping"]},
    {h:"Operations", items:["Maintenance coordination","Vendor management","Utilities automation","Emergency response"]},
    {h:"Governance", items:["Bylaws compliance","Board elections & notices","Annual/quarterly meetings","Owner communications"]},
  ];
  return (
    <section id="features" className="mx-auto max-w-7xl px-4 py-16">
      <h2 className="text-3xl md:text-4xl font-black tracking-tight">Full‑stack HOA management</h2>
      <div className="mt-6 grid md:grid-cols-3 gap-6">
        {cols.map((c,i)=> (
          <div key={i} className="rounded-3xl border p-6 bg-white">
            <h3 className="text-xl font-extrabold">{c.h}</h3>
            <ul className="mt-3 space-y-2 text-sm text-slate-700">
              {c.items.map((x,j)=> <li key={j}>• {x}</li>)}
            </ul>
          </div>
        ))}
      </div>
    </section>
  );
}

function Comparison(){
  const rows = [
    {k:"24/7 call, text, email (human)", us:true, others:true},
    {k:"No‑special‑assessment promise (budget discipline)", us:true, others:false},
    {k:">20% reserves target + live Google Drive financials", us:true, others:false},
    {k:"Two‑week onboarding with on‑site scan", us:true, others:false},
    {k:"Owner autopay setup (Buildium)", us:true, others:true},
    {k:"Quarterly board scorecard & roadmap", us:true, others:false},
    {k:"Transparent vendor/AP automation", us:true, others:true},
  ];
  return (
    <section className="mx-auto max-w-7xl px-4 py-16">
      <h2 className="text-3xl md:text-4xl font-black tracking-tight">How we stand out</h2>
      <div className="mt-6 overflow-x-auto rounded-2xl border">
        <table className="w-full text-left text-sm">
          <thead className="bg-slate-50 text-slate-600">
            <tr>
              <th className="p-3">Capability</th>
              <th className="p-3">HOA.help</th>
              <th className="p-3">Typical firms</th>
            </tr>
          </thead>
          <tbody>
            {rows.map((r,i)=> (
              <tr key={i} className="border-t">
                <td className="p-3 font-medium text-slate-800">{r.k}</td>
                <td className="p-3">{r.us ? "✓" : "—"}</td>
                <td className="p-3">{r.others ? "✓" : "—"}</td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
      <p className="mt-3 text-xs text-slate-500">Based on public service descriptions and our operating model; individual competitors may vary.</p>
    </section>
  );
}

function FAQ(){
  const faqs = [
    {q:"What size associations do you manage?", a:"Condo and HOA communities of all sizes in Chicagoland. We tailor staffing and cadence to your building's needs."},
    {q:"How fast can we switch?", a:"Most transitions complete in two weeks once we receive current records, bank access, and owner contact lists."},
    {q:"Do you replace our vendors?", a:"Not by default. We can keep your preferred vendors and simply professionalize scheduling, payment, and oversight."},
    {q:"What software do you use?", a:"Buildium for owner autopay and accounting, plus shared Google Drive for clear, real‑time docs and reports."},
  ];
  return (
    <section id="faq" className="mx-auto max-w-7xl px-4 py-16">
      <h2 className="text-3xl md:text-4xl font-black tracking-tight">FAQs</h2>
      <div className="mt-6 grid md:grid-cols-2 gap-6">
        {faqs.map((f,i)=> (
          <details key={i} className="rounded-2xl border p-5 bg-white">
            <summary className="cursor-pointer font-semibold">{f.q}</summary>
            <p className="mt-2 text-slate-600">{f.a}</p>
          </details>
        ))}
      </div>
    </section>
  );
}

function CTA(){
  return (
    <section className="relative overflow-hidden">
      <div className="absolute inset-0 -z-10 bg-[radial-gradient(60%_50%_at_20%_10%,#e2e8f0,transparent_60%)]"/>
      <div className="mx-auto max-w-7xl px-4 py-16 text-center">
        <h2 className="text-3xl md:text-4xl font-black tracking-tight">Ready to feel in control again?</h2>
        <p className="mt-2 text-slate-600 max-w-2xl mx-auto">Let’s schedule a 15–30 minute call to outline your HOA’s needs. We’ll propose a two‑week transition and a clear 3–6 month roadmap to your community’s Promised Land.</p>
        <div className="mt-6 flex flex-wrap gap-3 justify-center">
          <a href="#contact" className="rounded-2xl bg-slate-900 text-white px-6 py-3 font-semibold">Get My Proposal</a>
          <a href="sms:+13125551234" className="rounded-2xl border px-6 py-3 font-semibold">Text 24/7</a>
        </div>
      </div>
    </section>
  );
}

function Contact(){
  return (
    <section id="contact" className="mx-auto max-w-7xl px-4 py-16">
      <div className="rounded-3xl border p-6 bg-white grid md:grid-cols-2 gap-6">
        <div>
          <h2 className="text-3xl font-black tracking-tight">Request a proposal</h2>
          <p className="mt-2 text-slate-600">Tell us about your community and we’ll reply with a clear transition plan and pricing.</p>
          <ul className="mt-4 text-sm text-slate-700 space-y-2">
            <li>• Service area: Chicago & suburbs</li>
            <li>• Hours: 24/7 for owners & boards</li>
            <li>• Email: hello@hoa.help · Phone: (312) 555‑1234</li>
          </ul>
        </div>
        <form className="grid gap-3">
          <input className="rounded-xl border px-4 py-3" placeholder="Your name" required />
          <div className="grid grid-cols-2 gap-3">
            <input className="rounded-xl border px-4 py-3" placeholder="Email" type="email" required />
            <input className="rounded-xl border px-4 py-3" placeholder="Phone" type="tel" />
          </div>
          <input className="rounded-xl border px-4 py-3" placeholder="Community name & city" />
          <textarea className="rounded-xl border px-4 py-3" placeholder="What are your top 2–3 issues?" rows={4}></textarea>
          <button type="submit" className="rounded-2xl bg-slate-900 text-white px-5 py-3 font-semibold">Send</button>
          <p className="text-xs text-slate-500">By submitting, you agree to be contacted by HOA.help. We will never sell your data.</p>
        </form>
      </div>
    </section>
  );
}

function Footer(){
  return (
    <footer className="border-t">
      <div className="mx-auto max-w-7xl px-4 py-10 grid md:grid-cols-3 gap-8 text-sm">
        <div>
          <div className="text-lg font-black">HOA.help</div>
          <p className="mt-2 text-slate-600 max-w-sm">Illinois‑focused HOA & condo association management. Transparent, disciplined, and always responsive.</p>
        </div>
        <div>
          <div className="font-semibold">Services</div>
          <ul className="mt-2 space-y-1 text-slate-600">
            <li>Financial management</li>
            <li>Operations & maintenance</li>
            <li>Governance support</li>
            <li>Owner communications</li>
          </ul>
        </div>
        <div>
          <div className="font-semibold">Contact</div>
          <ul className="mt-2 space-y-1 text-slate-600">
            <li>hello@hoa.help</li>
            <li>(312) 555‑1234</li>
            <li>Chicago, IL</li>
          </ul>
        </div>
      </div>
      <div className="text-xs text-slate-500 text-center pb-8">© {new Date().getFullYear()} HOA.help — All rights reserved.</div>
    </footer>
  );
}

function StructuredData(){
  const jsonLd = {
    '@context': 'https://schema.org',
    '@type': 'Organization',
    name: 'HOA.help',
    url: 'https://hoa.help',
    areaServed: 'Chicago, IL',
    sameAs: [],
    contactPoint: [{
      '@type': 'ContactPoint',
      telephone: '+1-312-555-1234',
      contactType: 'customer support',
      availableLanguage: ['English'],
      areaServed: 'US-IL'
    }],
    description: 'Illinois-focused HOA & condo association management providing 24/7 support, disciplined budgeting, and >20% reserve targets.'
  };
  return (
    <script type="application/ld+json" dangerouslySetInnerHTML={{__html: JSON.stringify(jsonLd)}} />
  );
}

