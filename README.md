Saatnya kita merakit **README.md** yang legendaris untuk repositori GitHub-mu! 

Sebagai *Senior Data Scientist*, saya menyusun draf README ini dalam **Bahasa Inggris** karena portofolio GitHub berstandar global sangat disukai oleh *recruiter* teknologi dan perusahaan multinasional. Struktur ini dirancang dengan gaya **Executive-Ready**—menonjolkan angka keuangan, performa operasional, dan hasil uji statistik, bukan sekadar menampilkan kode.

Kamu cukup menyalin seluruh teks di dalam kotak kode di bawah ini langsung ke file **README.md** di repositori GitHub-mu:

```markdown
# 📦 Data-Driven Turnaround Strategy for JNE Express: SLA Recovery & Operational Cost Mitigation

## 📌 Executive Summary
This Capstone Project provides a comprehensive, end-to-end operational and financial audit of PT Tiki Jalur Nugraha Ekakurir (JNE Express) from first-mile pickup at retail agents to last-mile delivery. By combining descriptive, diagnostic, and inferential statistical analysis of approximately 300,000 transaction records, we identified three critical operational bottlenecks: a severe SLA crisis in premium services (74.71% failure rate), an operational cost hemorrhage in Cash-on-Delivery (COD) returns (25.52% return rate), and revenue leakage due to systemic data governance gaps. 

This project delivers a highly actionable, data-driven turnaround blueprint and phased implementation roadmap designed to reclaim lost profit margins, optimize delivery infrastructure, and restore brand trust.

---

## 🏢 Business Context & Problem Statement
PT Tiki Jalur Nugraha Ekakurir (JNE Express) is a leading logistics and express delivery provider in Indonesia, utilizing a complex **Hub-and-Spoke** operational network. As e-commerce volume scales, maintaining operational efficiency while containing costs has become a critical challenge. 

This audit was initiated to solve four core bottlenecks:
1. **SLA Underperformance:** Severe delivery delays that breach guaranteed Service Level Agreements (SLA), particularly in premium segments.
2. **COD Operational Risk:** Elevated Return-to-Sender (RTS) rates for COD transactions, causing kurirs to execute failed deliveries without revenue recovery.
3. **Revenue Leakage:** Loss of freight charges due to human error and manual weight entry anomalies at retail spokes.
4. **Data Governance Deficits:** Systemic tracking inconsistencies, such as logical timestamp errors and incomplete customer databases.

---

## 🛠️ Dataset & Tech Stack
* **Language:** Python 3.12
* **Data Wrangling:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Statistical Inference:** SciPy (Chi-Square Test of Independence, Pearson Correlation), Statsmodels (2-Proportion Z-Test)
* **Architecture:** Non-destructive data transformation pipeline maintaining an audit trail of raw inputs for forensic revenue recovery.

---

## 📊 Key Insights & Statistical Proofs

### 1. The SLA Crisis in Premium YES (Yakin Esok Sampai) Service
While OKE (0.00% late) and REG (1.56% late) services perform exceptionally well, JNE’s premium **YES (Next-Day)** service is in a critical state, with an **SLA Miss rate of 74.71%** (54,407 late packages).
To find the root cause, we bypassed operational excuses using inferential statistics:
* **Pearson Correlation (r = -0.02, p-value = 0.7492):** Proved absolutely **no correlation** between daily transaction volumes and late rates. Delays are *not* driven by seasonal shopping peaks or holiday overload.
* **Chi-Square Test of Independence (p-value = 0.3379):** Confirmed that SLA failures are **completely independent of regional provinces**. 
* **Diagnosis:** The SLA crisis is a **systemic infrastructure failure**. JNE fails to physically segregate and prioritize YES packages at sorting hubs, allowing them to get bottlenecked in standard REG/OKE processing lines.

### 2. The Financial Drain of COD Returns (RTS)
Cash-on-Delivery (COD) transactions exhibit a massive **25.52% Return-to-Sender (RTS) rate**, compared to just **5.09% for Prepaid** orders.
* **Chi-Square Test of Independence (p-value = 0.1982):** Proven that high RTS rates are **independent of destination cities**. 
* **Diagnosis:** High returns are not a localized geographic issue but a **systemic policy defect**. The frictionless return policy encourages poor buyer behavior across all markets, costing JNE double the operational delivery cost (forward and return transit) without collecting freight revenue. High-risk cities include Jakarta (26.28%), Denpasar (26.20%), and Palembang (25.70%).

### 3. Forensic Audit of Revenue Leakage & System Inefficiencies
* **Lost Tonnage:** Found **769 packages** entering the system with illegal weight inputs of $\le 0$ kg. 
* **Financial Impact:** Under a conservative model (minimum 1 kg charge), JNE lost Rp 19,225,000. However, treating negative weight as typing typos (e.g., -5 kg treated as 5 kg absolute weight) reveals a **true revenue leakage of Rp 61,037,500** from this sample alone, heavily concentrated in Jawa Barat (Rp 11.1M) and Sumatera (Rp 10.1M).
* **Data Errors:** Identified **7,473 packages with logical timestamp errors** (Delivered date occurred before Pickup date) due to scanner sync glitches.
* **Sales Blind Spot:** Detected **4,500+ missing customer profiles (15.26% database leakage)**. These profiles were preserved under an 'Unknown' category to prevent marketing bias while preserving high-volume retail leads for corporate B2B sales conversion.

---

## 💡 Strategic Blueprint & Implementation Roadmap

JNE should execute these targeted recommendations in a phased manner to preserve operational stability:

```
      [Q1 - YEAR 1]                    [Q2-Q4 - YEAR 1]                     [YEAR 2]
 ┌───────────────────────┐       ┌──────────────────────────┐       ┌───────────────────────┐
 │   Fase 1: Quick Wins  │ ─────>│ Fase 2: Pilot & Deploy   │ ─────>│ Fase 3: Nat. Expansion│
 └───────────────────────┘       └──────────────────────────┘       └───────────────────────┘
  • Launch COD Auto-Blacklist     • Deploy Locked POS UI/UX          • Scale YES Fast-Track
  • Introduce COD Return Ins.     • Establish Jawa YES Fast-Lane       to Sumatra, Kalimantan,
  • Develop Database Hard-Rules   • Implement Branch KPI Shift         and Sulawesi Hubs.
```

### Fase 1: Quick Wins & Development (Q1 - Year 1)
* **COD Risk Mitigation:** Build database hard-rules to automatically blacklist buyers with $\ge 5$ returns per year. Mandate a COD Return Insurance (0.2% of item value + Rp 5,000 per resi) for merchants to offload failed delivery overhead.
* **IT UI/UX Updates:** Develop a locked Point-of-Sale (POS) interface for retail agents, replacing free-text inputs with locked dropdown menus (to eliminate ~44% text typos) and restricting any weight entry $\le 0$ kg.

### Fase 2: Deployment & Pilot Project (Q2-Q4 - Year 1)
* **Software Roll-out:** Launch the upgraded POS system nationwide to block data errors at the source.
* **SLA YES Pilot Program (Jawa Hubs):** Jawa handles ~50% of JNE's premium volume. Establish a **Physical Fast-Track Lane** exclusively for YES packages at Jawa hubs. Transition Branch Managers' KPIs from "Total Volume" to "YES Clearance Speed before Midnight". 
* *Business Impact:* Reaching a realistic 15% SLA Miss target in Jawa will rescue **21,670 premium packages**, collapsing JNE's national SLA Miss rate from **74.71% down to 44.95%** in Year 1.

### Fase 3: National Expansion (Year 2)
* Replicate and scale the Jawa fast-track sorting blueprint to other high-volume regional hubs (Sumatera, Kalimantan, and Sulawesi).

---

## 💻 How to Run the Analysis
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/jne-logistics-turnaround.git
   ```
2. Navigate to the project folder and install dependencies:
   ```bash
   pip install pandas matplotlib seaborn scipy statsmodels
   ```
3. Open Jupyter Notebook or JupyterLab and run `Capstone_Project_3.ipynb` sequentially.
```

---
berkunjung ke GitHub-mu!

📊 **Langkah berikutnya:** Apakah kamu ingin kita langsung menyusun rancangan tulisan dan isi per-slide untuk **Slide Presentasi (PPT)** yang siap kamu bawakan di depan dosen penguji dan dewan direksi?
