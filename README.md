# FinancePort
// Portfolio-Quant-Finance.jsx
// Single-file React component (Tailwind CSS required in the project)
// How to use: paste into a React app (Create React App / Vite). Tailwind must be configured.
// Replace placeholder data (projects, skills, contacts) with your own.

import React, { useState } from 'react';
import {
  GitHub,
  Linkedin,
  Mail,
  Briefcase,
  Database,
  BarChart2,
} from 'lucide-react';

export default function QuantPortfolio() {
  const [tab, setTab] = useState('projects');

  const projects = [
    {
      title: 'Equity Factor Backtester',
      desc: 'Backtesting engine for equity factor strategies (momentum, value, quality) with transaction costs and slippage modelling.',
      tags: ['Python', 'Pandas', 'NumPy', 'Backtest'],
      link: '#',
    },
    {
      title: 'Volatility Surface Calibrator',
      desc: 'Calibrated SABR and local volatility surfaces; used for option pricing and Greeks estimation.',
      tags: ['C++', 'QuantLib', 'Calibration'],
      link: '#',
    },
    {
      title: 'Intraday Liquidity Model',
      desc: 'Microstructure model predicting liquidity and optimal execution schedules using XGBoost and time-series features.',
      tags: ['XGBoost', 'Time Series', 'Tick Data'],
      link: '#',
    },
  ];

  const skills = [
    { name: 'Python', level: 'Expert' },
    { name: 'C++', level: 'Advanced' },
    { name: 'Pandas / NumPy', level: 'Expert' },
    { name: 'Machine Learning', level: 'Advanced' },
    { name: 'Statistics & Econometrics', level: 'Advanced' },
    { name: 'QuantLib', level: 'Intermediate' },
    { name: 'SQL / Databases', level: 'Advanced' },
    { name: 'Git & CI', level: 'Advanced' },
  ];

  return (
    <div className="min-h-screen bg-slate-50 text-slate-900">
      <header className="max-w-5xl mx-auto p-6 flex items-center justify-between">
        <div className="flex items-center gap-4">
          <div className="rounded-full bg-gradient-to-br from-indigo-600 to-cyan-400 w-14 h-14 flex items-center justify-center text-white font-bold">AD</div>
          <div>
            <h1 className="text-2xl font-semibold">Adam D. — Quantitative Finance</h1>
            <p className="text-sm text-slate-600">Modeling • Research • Execution</p>
          </div>
        </div>

        <nav className="flex items-center gap-4">
          <a href="#projects" onClick={() => setTab('projects')} className={`px-3 py-2 rounded-md ${tab === 'projects' ? 'bg-slate-100' : 'hover:bg-slate-100'}`}>Projects</a>
          <a href="#skills" onClick={() => setTab('skills')} className={`px-3 py-2 rounded-md ${tab === 'skills' ? 'bg-slate-100' : 'hover:bg-slate-100'}`}>Skills</a>
          <a href="#contacts" onClick={() => setTab('contacts')} className={`px-3 py-2 rounded-md ${tab === 'contacts' ? 'bg-slate-100' : 'hover:bg-slate-100'}`}>Contacts</a>
        </nav>
      </header>

      <main className="max-w-5xl mx-auto p-6">
        {/* Hero */}
        <section className="grid grid-cols-1 md:grid-cols-3 gap-6 items-start mb-8">
          <div className="md:col-span-2 bg-white p-6 rounded-2xl shadow-sm">
            <h2 className="text-xl font-semibold mb-2">Hello — I'm Adam</h2>
            <p className="text-slate-600">Quantitative researcher focused on derivatives pricing, alpha-generation and execution algorithms. I build production-ready systems and rigorous backtests validated with robust risk controls.</p>

            <div className="mt-4 flex gap-3">
              <a className="inline-flex items-center gap-2 px-4 py-2 rounded-lg border" href="#projects" onClick={() => setTab('projects')}><Briefcase size={16}/> See projects</a>
              <a className="inline-flex items-center gap-2 px-4 py-2 rounded-lg border" href="mailto:adam@example.com"><Mail size={16}/> Contact me</a>
            </div>
          </div>

          <aside className="bg-white p-6 rounded-2xl shadow-sm">
            <h3 className="font-semibold mb-3">Quick stats</h3>
            <ul className="space-y-2 text-sm text-slate-600">
              <li><strong>Years:</strong> 4+ in quant roles</li>
              <li><strong>Languages:</strong> Python, C++, SQL</li>
              <li><strong>Focus:</strong> Options, Execution, Factor Models</li>
            </ul>

            <div className="mt-4 flex gap-3">
              <a className="inline-flex items-center gap-2 text-sm" href="#" aria-label="GitHub"><GitHub size={18}/></a>
              <a className="inline-flex items-center gap-2 text-sm" href="#" aria-label="LinkedIn"><Linkedin size={18}/></a>
            </div>
          </aside>
        </section>

        {/* Tabs content */}
        <section className="bg-white p-6 rounded-2xl shadow-sm">
          <div className="flex gap-4 mb-6">
            <button className={`px-4 py-2 rounded-md ${tab === 'projects' ? 'bg-indigo-600 text-white' : 'border'}`} onClick={() => setTab('projects')}>Projects</button>
            <button className={`px-4 py-2 rounded-md ${tab === 'skills' ? 'bg-indigo-600 text-white' : 'border'}`} onClick={() => setTab('skills')}>Skills</button>
            <button className={`px-4 py-2 rounded-md ${tab === 'contacts' ? 'bg-indigo-600 text-white' : 'border'}`} onClick={() => setTab('contacts')}>Contacts</button>
          </div>

          {tab === 'projects' && (
            <div id="projects">
              <h3 className="text-lg font-semibold mb-4">Selected projects</h3>
              <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                {projects.map((p) => (
                  <article key={p.title} className="p-4 border rounded-lg bg-gray-50">
                    <h4 className="font-semibold">{p.title}</h4>
                    <p className="text-sm text-slate-600 my-2">{p.desc}</p>
                    <div className="flex flex-wrap gap-2 text-xs">
                      {p.tags.map((t) => (
                        <span key={t} className="px-2 py-1 bg-white border rounded-full">{t}</span>
                      ))}
                    </div>
                    <div className="mt-3">
                      <a href={p.link} className="text-sm underline">Read more</a>
                    </div>
                  </article>
                ))}
              </div>
            </div>
          )}

          {tab === 'skills' && (
            <div id="skills">
              <h3 className="text-lg font-semibold mb-4">Technical skills</h3>
              <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
                <div>
                  <h4 className="font-medium">Programming & Tools</h4>
                  <ul className="mt-2 space-y-2 text-sm text-slate-600">
                    {skills.slice(0,4).map(s => (
                      <li key={s.name} className="flex justify-between"><span>{s.name}</span><span className="text-xs text-slate-500">{s.level}</span></li>
                    ))}
                  </ul>
                </div>

                <div>
                  <h4 className="font-medium">Quant & Data</h4>
                  <ul className="mt-2 space-y-2 text-sm text-slate-600">
                    {skills.slice(4).map(s => (
                      <li key={s.name} className="flex justify-between"><span>{s.name}</span><span className="text-xs text-slate-500">{s.level}</span></li>
                    ))}
                  </ul>
                </div>
              </div>

              <div className="mt-6">
                <h4 className="font-medium">Visuals</h4>
                <div className="mt-3 grid grid-cols-1 md:grid-cols-3 gap-4">
                  <div className="p-4 border rounded-lg">
                    <div className="flex items-center gap-3"><BarChart2 size={18}/><h5 className="font-semibold">Backtests</h5></div>
                    <p className="text-sm text-slate-600 mt-2">Robust reporting and walk-forward analysis.</p>
                  </div>

                  <div className="p-4 border rounded-lg">
                    <div className="flex items-center gap-3"><Database size={18}/><h5 className="font-semibold">Data Pipelines</h5></div>
                    <p className="text-sm text-slate-600 mt-2">Automated ingestion, cleaning and feature engineering at scale.</p>
                  </div>

                  <div className="p-4 border rounded-lg">
                    <div className="flex items-center gap-3"><GitHub size={18}/><h5 className="font-semibold">Reproducibility</h5></div>
                    <p className="text-sm text-slate-600 mt-2">Unit-tested components and CI for model deployment.</p>
                  </div>
                </div>
              </div>
            </div>
          )}

          {tab === 'contacts' && (
            <div id="contacts">
              <h3 className="text-lg font-semibold mb-4">Get in touch</h3>
              <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                  <form className="space-y-3">
                    <div>
                      <label className="block text-sm">Name</label>
                      <input className="w-full mt-1 p-2 border rounded-md" placeholder="Your name" />
                    </div>

                    <div>
                      <label className="block text-sm">Email</label>
                      <input className="w-full mt-1 p-2 border rounded-md" placeholder="you@example.com" />
                    </div>

                    <div>
                      <label className="block text-sm">Message</label>
                      <textarea className="w-full mt-1 p-2 border rounded-md" rows={5} placeholder="Hi, I'd like to talk about..." />
                    </div>

                    <div>
                      <button type="button" className="px-4 py-2 rounded-md bg-indigo-600 text-white">Send message</button>
                    </div>
                  </form>
                </div>

                <aside className="p-4 border rounded-lg bg-gray-50">
                  <h4 className="font-medium mb-2">Direct</h4>
                  <p className="text-sm text-slate-600">adam@example.com</p>
                  <p className="text-sm text-slate-600">+33 6 12 34 56 78</p>

                  <h4 className="font-medium mt-4">Social</h4>
                  <div className="flex gap-3 mt-2">
                    <a href="#" aria-label="GitHub" className="inline-flex items-center gap-2"><GitHub size={16}/> GitHub</a>
                    <a href="#" aria-label="LinkedIn" className="inline-flex items-center gap-2"><Linkedin size={16}/> LinkedIn</a>
                  </div>
                </aside>
              </div>
            </div>
          )}
        </section>

        <footer className="mt-8 text-center text-sm text-slate-500">© {new Date().getFullYear()} Adam D. — Quantitative Finance</footer>
      </main>
    </div>
  );
}
