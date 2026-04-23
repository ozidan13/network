# 🌐 Network Mastery — إتقان الشبكات
## Complete Implementation Plan: Zero to Hero Networking Platform

---

> [!IMPORTANT]
> This plan is built from **direct analysis of the real Database Mastery codebase** — not just its design document. Every pattern, component, CSS class, and file structure described here is extracted from *actual implemented HTML files* (Unit1–Unit10) and `css/global-db.css`. This is a true sibling project.

---

## 🔍 Database Mastery: What Was Actually Built (Real Pattern Analysis)

Before defining the Network platform, here is what the DB project *actually* did — the ground truth from inspecting the real files:

### Real File Sizes (Complexity Gauge)
| Unit | Files | Avg Size | Complexity |
|------|-------|----------|-----------|
| Unit1 | 5 | ~41KB | Medium — story + visualization + quiz |
| Unit2 | 5 | ~58KB | High — ER diagram builders, interactive |
| Unit3 | 5 | ~54KB | High — SQL blocks, color-coded syntax, quizzes |
| Unit4 | 4 | ~47KB | Medium-High |
| Unit5 | 4 | ~38KB | Medium |
| Unit6 | 5 | ~37KB | Medium — code labs |
| Unit7 | 4 | ~34KB | Medium |
| Unit8 | 4 | ~34KB | Medium |
| Unit9 | 4 | ~33KB | Medium |
| Unit10 | 4 | ~27KB | Medium — capstone |

> **Key insight:** `why_databases.html` is the BIGGEST lesson at 75KB — it's the hook that sets the tone for everything. Network Mastery's `why_networks.html` must be equally powerful.

---

### ✅ Confirmed Real Implementation Patterns

#### 1. HTML Page Structure (from actual files)
```html
<!DOCTYPE html>
<html lang="en" class="scroll-smooth" dir="ltr">  <!-- LTR for lesson pages -->
<head>
    <!-- Cairo + Inter + Fira Code -->
    <!-- Font Awesome 6.4.0 -->
    <!-- AOS 2.3.1 -->
    <!-- ../css/global-db.css  (shared across all lessons) -->
    <style>/* Lesson-specific only */</style>
</head>
<body>
    <!-- 1. Fixed Navbar (.lesson-nav-bar) — back btn + section anchors -->
    <!-- 2. Reading Progress Bar (.progress-bar-container) -->
    <!-- 3. Hero (.lesson-hero) — badge + h1 gradient + subtitle (RTL) + desc -->
    <!-- 4. Sections alternating: .lesson-section | .lesson-section.alt-bg -->
    <!-- 5. Each section: .section-header (h2 Arabic + .en-sub English) -->
    <!-- 6. Content: .glass-card > .rtl-block (Arabic explanations) -->
    <!-- 7. Specialized components: quizzes, visualizations, code blocks -->
    <!-- 8. Bottom nav (.lesson-bottom-nav) — prev/next lesson links -->
    <!-- 9. Footer (unit + lesson name) -->
    <!-- AOS init + reading progress JS + lesson-specific JS -->
</body>
</html>
```

#### 2. Portal (index.html) — RTL page
- `<html lang="ar" dir="rtl">` — only the portal is full RTL
- `#particle-canvas` — floating emerald/cyan particles with connections
- `.aurora-1/2/3` — floating glow blobs (emerald, cyan, purple)
- `.hero-section` → logo + gradient title + subtitle + stats bar
- `.units-container` — CSS grid (5×2 desktop, 2×N tablet, 1×N mobile)
- `.unit-card.unit-N` — each with `--unit-color` and `--unit-glow` CSS vars
- Card tilt effect on `mousemove`
- `.lesson-item` links — icon + text + chevron

#### 3. Global CSS (`css/global-db.css`) — 435 lines, covers:
- CSS custom properties for all 10 unit colors
- `.rtl-block` + `.english` + `.ltr-island` — bilingual system
- `.glass-card` / `.glass-heavy` / `.glass-light` / `.glass-nav`
- `.step-box` / `.note` / `.law-box` / `.warning-box`
- `.code-box` with `::before "💻 الكود:"` auto-label
- `.comparison-table` — RTL-aware table styling
- Aurora keyframes, gradient text animation
- Custom scrollbar, RTL arrow flip

#### 4. Lesson-Specific Components (per-lesson `<style>` blocks)
Each lesson defines its own component CSS inside `<style>`:
- `why_databases.html` → `.scenario-card`, `.mini-table`, `.problem-card`, `.solution-card`, `.dbms-visual`, `.dbms-layer`, `.quiz-container`
- `joins_mastery.html` → `.join-section`, `.join-badge`, `.venn-wrap`, `.data-table`, `.sql-block`, `.sql-bar`, `.sdot`, `.kw/.tb/.col/.str/.num/.cmt` (syntax highlighting), `.practice-block`, `.quiz-card`

#### 5. Content Style — El Daheeh (Confirmed from actual text)
- Opens with a shocking Egyptian scenario ("تخيل إنك مسؤول عن 50,000 طالب")
- Uses `<div class="rtl-block">` for all Arabic paragraphs
- Inline English terms: `<span class="english">JOIN</span>`
- Highlights: `<span class="hl-amber">`, `<span class="hl-cyan">`, `<span class="hl-red">`
- Step boxes: `<div class="step-box">` with border accent
- Notes: `<div class="note">` (yellow), `<div class="law-box">` (blue), `<div class="warning-box">` (red)
- Interactive quiz: click options → `.correct` / `.wrong` classes + feedback div

---

## 🎯 Network Mastery Vision

**A world-class, standalone platform that takes any student — from someone who never heard of TCP/IP to a network engineer ready for CCNA certification — through the complete networking stack using the same battle-tested patterns as Database Mastery.**

### Target Audience (Dual-Track)
| Track | Who | What They Need |
|-------|-----|----------------|
| 🎓 **Academic Track** | CS/IT students at Egyptian universities (FCIS, FCAI, GUC, AAST, etc.) | OSI model, TCP/IP, subnetting, routing algorithms — exactly what they study in Computer Networks courses using Forouzan / Tanenbaum |
| 💼 **Career Track** | Self-learners targeting sysadmin, DevOps, cloud, cybersecurity roles | Practical packet analysis, Cisco CLI simulation, real troubleshooting, CCNA prep |

### Design Philosophy
- **Same glass-morphism UI** — cloned from DB Mastery with new color palette (Sky Blue / Electric Cyan theme)
- **Same El Daheeh storytelling** — Egyptian Arabic with English technical terms
- **New unique interactives** — Packet simulators, Protocol animators, Network topology builders, Subnetting calculators
- **OSI-themed color system** — each unit gets a layer-inspired color

---

## 🎨 Complete Design System

### Network Unit Colors (adapted from DB approach)

| Unit | Topic | Primary | Light | Dark | Glow |
|------|-------|---------|-------|------|------|
| 1 | Intro | `#06B6D4` (Cyan) | `#22D3EE` | `#0891B2` | `rgba(6,182,212,0.2)` |
| 2 | OSI Model | `#3B82F6` (Blue) | `#60A5FA` | `#1D4ED8` | `rgba(59,130,246,0.2)` |
| 3 | Physical Layer | `#8B5CF6` (Purple) | `#A78BFA` | `#6D28D9` | `rgba(139,92,246,0.2)` |
| 4 | Data Link | `#F59E0B` (Amber) | `#FBBF24` | `#D97706` | `rgba(245,158,11,0.2)` |
| 5 | Network Layer | `#10B981` (Emerald) | `#34D399` | `#059669` | `rgba(16,185,129,0.2)` |
| 6 | Transport Layer | `#EF4444` (Red) | `#F87171` | `#DC2626` | `rgba(239,68,68,0.2)` |
| 7 | Application Layer | `#F97316` (Orange) | `#FB923C` | `#EA580C` | `rgba(249,115,22,0.2)` |
| 8 | Network Security | `#EC4899` (Pink) | `#F472B6` | `#DB2777` | `rgba(236,72,153,0.2)` |
| 9 | Practical Skills | `#14B8A6` (Teal) | `#2DD4BF` | `#0D9488` | `rgba(20,184,166,0.2)` |
| 10 | Capstone | `#D946EF` (Fuchsia) | `#E879F9` | `#C026D3` | `rgba(217,70,239,0.2)` |

### Global CSS File: `css/global-net.css`

This is the ONLY change from DB Mastery's CSS — rename and update colors:

```css
/* Network Mastery — Global Design System (global-net.css) */
:root {
    /* Same background/text/border tokens as DB Mastery */
    --bg-body:       #020617;
    --bg-card:       #0F172A;
    --bg-alt:        #1E293B;
    --bg-hover:      rgba(255, 255, 255, 0.04);
    --text-primary:  #F1F5F9;
    --text-body:     #E2E8F0;
    --text-muted:    #94A3B8;
    --text-faint:    #64748B;
    --text-ghost:    #475569;
    --border-subtle: rgba(255, 255, 255, 0.06);
    --border-light:  rgba(255, 255, 255, 0.1);
    --border-hover:  rgba(255, 255, 255, 0.15);

    /* Network Unit Colors */
    --unit-1: #06B6D4;  --unit-1-light: #22D3EE;  --unit-1-dark: #0891B2;  --unit-1-glow: rgba(6,182,212,0.2);
    --unit-2: #3B82F6;  --unit-2-light: #60A5FA;  --unit-2-dark: #1D4ED8;  --unit-2-glow: rgba(59,130,246,0.2);
    --unit-3: #8B5CF6;  --unit-3-light: #A78BFA;  --unit-3-dark: #6D28D9;  --unit-3-glow: rgba(139,92,246,0.2);
    --unit-4: #F59E0B;  --unit-4-light: #FBBF24;  --unit-4-dark: #D97706;  --unit-4-glow: rgba(245,158,11,0.2);
    --unit-5: #10B981;  --unit-5-light: #34D399;  --unit-5-dark: #059669;  --unit-5-glow: rgba(16,185,129,0.2);
    --unit-6: #EF4444;  --unit-6-light: #F87171;  --unit-6-dark: #DC2626;  --unit-6-glow: rgba(239,68,68,0.2);
    --unit-7: #F97316;  --unit-7-light: #FB923C;  --unit-7-dark: #EA580C;  --unit-7-glow: rgba(249,115,22,0.2);
    --unit-8: #EC4899;  --unit-8-light: #F472B6;  --unit-8-dark: #DB2777;  --unit-8-glow: rgba(236,72,153,0.2);
    --unit-9: #14B8A6;  --unit-9-light: #2DD4BF;  --unit-9-dark: #0D9488;  --unit-9-glow: rgba(20,184,166,0.2);
    --unit-10:#D946EF;  --unit-10-light:#E879F9;  --unit-10-dark:#C026D3; --unit-10-glow:rgba(217,70,239,0.2);
}
/* All other rules identical to global-db.css */
/* Update gradient text to network theme: */
.text-gradient-net {
    background: linear-gradient(135deg, #06B6D4 0%, #3B82F6 40%, #8B5CF6 70%, #EC4899 100%);
    /* ... same animation */
}
/* Aurora blobs: cyan + blue instead of emerald + cyan */
.aurora-1 { background: rgba(6, 182, 212, 0.12); }
.aurora-2 { background: rgba(59, 130, 246, 0.10); }
.aurora-3 { background: rgba(139, 92, 246, 0.08); }
/* Particle hues for portal canvas: */
/* this.hue = Math.random() > 0.5 ? 195 : 220;  // cyan=195, blue=220 */
```

### Portal Logo
```html
<div class="net-logo">
    <i class="fas fa-network-wired"></i>
</div>
<!-- Gradient: cyan → blue -->
```

### Gradient Text for Hero
```
Network Mastery — إتقان الشبكات
```

---

## 📚 Complete Curriculum — 10 Units

---

### 🌐 UNIT 1: عالم الشبكات — The World of Networks
**Level:** Absolute Beginner | **Lessons:** 5 | **Color:** `#06B6D4` (Cyan)

> *"قبل ما نعرف إزاي الإنترنت بيشتغل، لازم نفهم ليه محتاجين الشبكات أصلاً"*

#### Lesson 1.1: `why_networks.html` — ليه محتاجين شبكات؟
- **Hook:** "تخيل إنك في جامعة القاهرة والدكتور عايز يبعتلك الملف. بعتهولك على USB. طب لو 500 طالب؟ 😅"
- **Concept:** The problem without networks — isolated computers, no sharing, no communication
- **Visualization:** **Interactive animation** — isolated computers vs. networked computers (canvas-based)
  - Click "بدون شبكة" → shows isolated computers struggling
  - Click "مع شبكة" → shows instant data flow between all machines
- **Real-world examples:**
  - نظام التنسيق المصري — كيف بيوصل نتائج 800K طالب في نفس الوقت
  - WhatsApp — رسالة بتتبعت من موبايلك لـ 3 قارات في milliseconds
  - Vodafone مصر — شبكة بتخدم 40+ مليون مستخدم
- **Problem cards:** (same pattern as DB problem-card component)
  - ❌ عزل الأجهزة | ❌ عدم مشاركة الملفات | ❌ تكلفة الطباعة | ❌ مفيش تواصل
- **Solution cards:** ✅ المشاركة | ✅ التواصل | ✅ المركزية | ✅ الاقتصاد
- **Quiz:** 3 questions about basic networking concepts

#### Lesson 1.2: `network_types.html` — أنواع الشبكات
- **Concept:** PAN → LAN → MAN → WAN → Internet
- **Visualization:** **Interactive map** — zoom from room → building → city → country → world
  - Each level highlights with its color, shows real examples
- **Egyptian examples:**
  - PAN: Bluetooth بين موبايلك وسماعتك
  - LAN: شبكة الكلية
  - MAN: شبكة مترو القاهرة
  - WAN: شبكة بنك الأهلي بين فروعه
  - Internet: كل ده مع بعض!
- **Comparison table:** Scope, speed, ownership, examples
- **Interactive quiz:** Match the network type to the scenario

#### Lesson 1.3: `network_topologies.html` — طوبولوجيا الشبكات
- **Concept:** Bus, Star, Ring, Mesh, Hybrid topologies
- **Visualization:** **Live topology builder** — click buttons to switch between topologies
  - Canvas draws nodes and connections dynamically
  - Shows single-point-of-failure simulation
- **Analogy:** "تخيل عزبة فيها ناس بيتكلموا مع بعض — الـ topology هي طريقة ترتيب البيتوت"
- **Pros/Cons cards** for each topology
- **Interactive:** "فيه عطل في الكابل — أي topology هتأثر؟" simulation

#### Lesson 1.4: `network_hardware.html` — عتاد الشبكات
- **Concept:** Hub, Switch, Router, Gateway, Firewall, Access Point, Modem
- **Visualization:** **Interactive device explorer** — click each device, see:
  - Physical appearance (SVG icon)
  - What it does (animated explanation)
  - OSI layer it operates at
  - Real-world example
- **Analogy:**
  - Hub = "ميكروفون في مؤتمر — لما حد يتكلم كل الناس تسمعه"
  - Switch = "بدالة تليفونات — بيوصل المتكلم بالمستمع بس"
  - Router = "باب البوابة اللي بيعرف الطريق للعالم"
- **Interactive comparison** table: Hub vs Switch vs Router

#### Lesson 1.5: `network_history.html` — تاريخ الشبكات
- **Concept:** ARPANET (1969) → TCP/IP (1983) → WWW (1991) → WiFi (1997) → Mobile Internet → 5G
- **Visualization:** **Animated timeline** — milestones pop up as you scroll
- **Tribute:** Vint Cerf & Bob Kahn (fathers of the Internet), Tim Berners-Lee (WWW)
- **Fun facts:** أول رسالة على ARPANET كانت "LO" — النظام انهار قبل ما يكمل "LOGIN"!
- **Egyptian context:** تاريخ الإنترنت في مصر — من أول ارتباط 1993 لحد الإنترنت ده

---

### 🔵 UNIT 2: نموذج OSI والـ TCP/IP — The Reference Models
**Level:** Beginner | **Lessons:** 5 | **Color:** `#3B82F6` (Blue)

> *"الـ OSI Model هو الـ blueprint اللي بناء عليه كل شبكة في الدنيا"*

#### Lesson 2.1: `osi_model.html` — نموذج OSI
- **Concept:** The 7 layers — Physical, Data Link, Network, Transport, Session, Presentation, Application
- **Hook:** "تخيل بتبعت رسالة لحبيبتك. الرسالة دي بتعدي 7 محطات قبل ما توصل — ومن الجهة التانية بتعدي 7 محطات تانية. ده الـ OSI Model."
- **Visualization:** **Interactive 7-layer stack**
  - Click each layer → expands with:
    - Arabic name + English name
    - What it does
    - Protocol examples
    - Device that operates at this layer
    - Real-world analogy
  - **Packet encapsulation animation** — watch a message get wrapped at each layer
- **Mnemonics:**
  - Top to bottom: "أنا ضايع في الشبكة نهائي" = Application, Presentation, Session, Transport, Network, Data Link, Physical
  - Bottom to top: "ضربة شبكة طحنتني في الأشعة النوانية"
- **Data PDU naming:** Data → Segment → Packet → Frame → Bits

#### Lesson 2.2: `tcp_ip_model.html` — نموذج TCP/IP
- **Concept:** The 4-layer practical model vs. OSI's 7 layers
- **Comparison visualizer:** Side-by-side animated comparison: OSI ↔ TCP/IP mapping
- **Layers:** Application → Transport → Internet → Network Access
- **Why TCP/IP won:** It's what the Internet actually uses
- **Protocol mapping table:**
  | TCP/IP Layer | Protocols |
  |---|---|
  | Application | HTTP, HTTPS, FTP, SMTP, DNS, DHCP |
  | Transport | TCP, UDP |
  | Internet | IP, ICMP, ARP |
  | Network Access | Ethernet, WiFi |

#### Lesson 2.3: `encapsulation.html` — التغليف وإزالة التغليف
- **Concept:** How data travels down the sender's stack, across the wire, up the receiver's stack
- **Animation:** **Step-by-step packet journey** canvas visualization
  - Source computer → each layer adds header → wire → destination → each layer strips header
- **Headers explained:** What each layer adds and why
- **Real example:** "بتبعت email — تعالى نشوف الرحلة الكاملة من Outlook لحد Gmail"
- **Interactive:** Build a packet manually — drag and drop headers

#### Lesson 2.4: `protocols_intro.html` — مقدمة في البروتوكولات
- **Concept:** What is a protocol? Why do we need standards?
- **Analogy:** "الـ Protocol زي اللغة. أنا بتكلم عربي وإنت بتكلم ياباني — محدش فاهم محدش. الـ Protocol هو الاتفاق على لغة مشتركة"
- **Key properties:** Syntax, Semantics, Timing
- **Standards bodies:** IEEE, IETF, ISO — وليهم علاقة بمصر؟
- **RFC system:** "كيف يتم الاتفاق على بروتوكول جديد في العالم"

#### Lesson 2.5: `addressing_basics.html` — أساسيات العناوين
- **Concept:** Physical (MAC), Logical (IP), Port addresses
- **Analogy:**
  - IP address = عنوان البيت
  - MAC address = الرقم القومي للكارت
  - Port = رقم الشقة داخل العمارة
- **ARP process:** How MAC is discovered from IP — animated
- **Interactive:** "فكّ اللغز — الحزمة دي رايحة فين؟" — decode a packet's addresses

---

### 🟣 UNIT 3: الطبقة الفيزيائية — Physical Layer
**Level:** Beginner → Intermediate | **Lessons:** 4 | **Color:** `#8B5CF6` (Purple)

> *"قبل ما يحصل أي حاجة — لازم يكون فيه سلك أو موجة بتنقل الداتا"*

#### Lesson 3.1: `transmission_media.html` — وسائط النقل
- **Concept:** Guided (Twisted Pair, Coaxial, Fiber Optic) vs. Unguided (Radio, Microwave, Infrared)
- **Visualization:** **Interactive cable explorer**
  - Cross-section SVG of each cable type, animated signal traveling through it
  - Speed comparison bar chart (updating live)
- **Examples:** كابلات RJ-45 اللي في المختبرات، الـ Fiber Optic اللي بيجي من Telecom Egypt
- **Comparison table:** Media type, speed, distance, cost, interference

#### Lesson 3.2: `signal_encoding.html` — الإشارات والترميز
- **Concept:** Analog vs. Digital signals, encoding schemes (NRZ, Manchester, 4B/5B)
- **Visualization:** **Live oscilloscope** — Canvas that draws signal waveforms
  - Input binary sequence → see how it's encoded in each scheme
- **Concept:** Bandwidth, throughput, latency — explained with Egyptian road analogy
  - "الـ Bandwidth زي عرض الطريق — الـ Throughput زي الحركة الفعلية فيه"
- **Nyquist theorem:** Maximum data rate over noise-free channel
- **Shannon's theorem:** Maximum data rate over noisy channel (with interactive calculator)

#### Lesson 3.3: `multiplexing.html` — المضاعفة (Multiplexing)
- **Concept:** FDM, TDM, WDM, CDMA — sharing the medium
- **Analogy:**
  - FDM = "FM Radio — كل محطة على تردد مختلف"
  - TDM = "دور المحطات — كل واحدة ليها وقت محدد"
  - WDM = "ألوان ضوء مختلفة في نفس الـ fiber"
- **Animation:** Watch multiple signals share one wire simultaneously
- **Egyptian context:** كيف بعتلك Telecom Egypt الإنترنت والتليفون على نفس الكابل

#### Lesson 3.4: `switching_transmission.html` — أنواع التبديل
- **Concept:** Circuit Switching vs. Packet Switching vs. Message Switching
- **Analogy:**
  - Circuit Switching = "مكالمة تليفون قديمة — الخط محجوز طول المكالمة"
  - Packet Switching = "الإنترنت — كل packet بيلاقي طريقه لوحده"
- **Animation:** Send a file via circuit vs. packet switching — see the efficiency difference
- **Why packet switching won:** Resilience, efficiency, scalability

---

### 🟡 UNIT 4: طبقة الوصول للبيانات — Data Link Layer
**Level:** Intermediate | **Lessons:** 5 | **Color:** `#F59E0B` (Amber)

> *"الـ Data Link Layer هي اللي بتضمن إن الداتا توصل من device لـ device على نفس الشبكة سليمة"*

#### Lesson 4.1: `framing_error.html` — التأطير واكتشاف الأخطاء
- **Concept:** Framing, error detection (Parity, CRC, Checksum), error correction (Hamming)
- **Hook:** "لو بعتلك الرقم 42 وأنا كتبت 24 بالغلط — إزاي تعرف إن فيه غلطة؟"
- **Interactive CRC calculator:** Input data → see CRC computation step by step
- **Visualization:** Frame structure with flags, header, data, trailer labeled

#### Lesson 4.2: `mac_addresses.html` — عناوين MAC والـ Ethernet
- **Concept:** MAC address structure (48-bit, OUI + NIC), Ethernet frame structure
- **Visualization:** **MAC address dissector** — input any MAC → see manufacturer, type, broadcast bit
- **Ethernet frame:** Animated frame with each field highlighted and explained
- **Collision domains:** CSMA/CD explained with Egyptian intersection analogy
  - "زي تقاطع من غير إشارة — كل حد بيحاول يعدي في نفس الوقت"
- **ARP table:** How switches learn MAC addresses

#### Lesson 4.3: `switching_vlans.html` — السويتش والـ VLANs
- **Concept:** How switches work (MAC table, flooding, forwarding), VLANs
- **Visualization:** **Live switch simulation**
  - See MAC address table being populated as frames are sent
  - VLAN segmentation — frame from VLAN 10 can't reach VLAN 20 without router
- **Analogy:** "الـ VLAN زي بناية فيها أقسام مختلفة — المبيعات والمحاسبة في نفس البناية بس منفصلين"
- **Trunk ports vs. Access ports:** Visual diagram

#### Lesson 4.4: `spanning_tree.html` — Spanning Tree Protocol
- **Concept:** Why loops are deadly + STP election process + port states
- **Visualization:** **STP simulator** — network with loops → STP eliminates them step by step
- **Root bridge election:** How the bridge with lowest BID wins
- **Port states:** Blocking → Listening → Learning → Forwarding
- **Modern alternatives:** RSTP, MSTP — why they're faster

#### Lesson 4.5: `wifi_wireless.html` — الشبكات اللاسلكية WiFi
- **Concept:** 802.11 standards (a/b/g/n/ac/ax), CSMA/CA, channels, bands
- **Visualization:** **WiFi channel visualizer** — 2.4GHz vs 5GHz channels, overlap
- **SSID, BSSID, Association process** — animated
- **Security:** WEP (broken) → WPA → WPA2 → WPA3
- **Egyptian context:** "ليه الإنترنت في الكافيه ببطء لما فيه ناس كتير"

---

### 🟢 UNIT 5: طبقة الشبكة — Network Layer
**Level:** Intermediate | **Lessons:** 6 | **Color:** `#10B981` (Emerald)

> *"طبقة الشبكة هي اللي بتحدد الطريق — وبدونها الداتا ماتعرفش ترحل من مصر لأمريكا"*

#### Lesson 5.1: `ip_addressing.html` — عناوين IP
- **Concept:** IPv4 structure (32-bit, 4 octets), classes, special addresses
- **Visualization:** **IP address visualizer** — binary ↔ decimal conversion, live
- **Classes:** A (1-126), B (128-191), C (192-223), D (Multicast), E (Reserved)
- **Special addresses:** 127.0.0.1 (loopback), 255.255.255.255 (broadcast), 0.0.0.0
- **Interactive:** "اكتب IP وشوف طبقتها ونوع العنوان"

#### Lesson 5.2: `subnetting.html` — التقسيم الشبكي (Subnetting) ⭐
- **The most important network lesson** — like Normalization for databases
- **Concept:** Subnet masks, CIDR notation, subnetting calculations
- **Hook:** "إداك دكاترة الجامعة شبكة 192.168.1.0/24 — وقالولك قسمها لـ 4 شبكات متساوية. هتعمل إيه؟"
- **Visualization:** **Interactive subnetting calculator**
  - Input: IP address + prefix length
  - Output: Network address, Broadcast, Host range, Number of hosts — all computed visually
  - **Binary representation** shown below each step
- **CIDR explained:** Why /24 means 256 addresses
- **Worked examples:** Shorten subnets, find the right subnet for a given host
- **Practice:** 10 progressive subnetting challenges with auto-checking

#### Lesson 5.3: `ipv6.html` — الجيل الجديد IPv6
- **Concept:** Why IPv4 is exhausted, IPv6 128-bit addresses, notation rules
- **Visualization:** Compare IPv4 (4 billion) vs IPv6 (340 undecillion) address space — cosmic scale
- **Address types:** Unicast, Multicast, Anycast (no more Broadcast!)
- **Transition:** Dual Stack, Tunneling, NAT64
- **Egyptian context:** مصر وتبني IPv6 — ليه أهم من ما بنفكر

#### Lesson 5.4: `routing_basics.html` — التوجيه (Routing)
- **Concept:** Static vs. Dynamic routing, routing table, next-hop
- **Visualization:** **Packet routing animation** — choose source/destination → watch packet choose path
- **Router decision process:** "ييجي الـ packet — الـ router بيبص في الـ routing table زي ما بتبص في الخريطة"
- **Default route:** The gateway of last resort
- **Routing table reading:** Hands-on with output examples

#### Lesson 5.5: `routing_protocols.html` — بروتوكولات التوجيه
- **Concept:** RIP, OSPF, EIGRP, BGP — distance vector vs. link state
- **Visualization:** **Routing convergence animation**
  - RIP: slow convergence, hop count metric
  - OSPF: fast convergence, cost metric, Dijkstra's SPF
  - BGP: the protocol that runs the Internet
- **Analogy:**
  - RIP = "اسأل جارك — اللي أقرب ليه قوله"
  - OSPF = "كل حد عارف خريطة كاملة للشبكة"
  - BGP = "التفاوض السياسي بين دول الإنترنت"
- **Dijkstra's algorithm:** Step-by-step visual execution on a graph

#### Lesson 5.6: `nat_dhcp.html` — NAT والـ DHCP
- **Concept:** NAT (Static, Dynamic, PAT/Masquerade), DHCP process
- **NAT visualization:** "500 جهاز في الشركة — كلهم بيخرجوا للإنترنت باستخدام IP واحد"
- **DHCP DORA:** **Animated 4-step process** — Discover, Offer, Request, Acknowledge
- **Interactive:** DHCP server simulator — allocate and release IPs
- **PAT table:** Port Address Translation mapped — how each connection tracked

---

### 🔴 UNIT 6: طبقة النقل — Transport Layer
**Level:** Intermediate → Advanced | **Lessons:** 4 | **Color:** `#EF4444` (Red)

> *"الـ Transport Layer هي المسؤولة عن التسليم الموثوق — أو السريع — من تطبيق لتطبيق"*

#### Lesson 6.1: `tcp_udp.html` — TCP vs UDP
- **The most critical transport lesson**
- **Analogy:**
  - TCP = "DHL — بيوصلك الطرد ويجيب توقيع. أبطأ بس مضمون."
  - UDP = "بتبعت جواب بالبريد العادي — مش عارف وصل ولا لأ. أسرع بس."
- **Visualization:** **Side-by-side connection race**
  - TCP: handshake → data → ACKs → teardown (animated)
  - UDP: shoot and forget (animated)
- **TCP Header:** Source port, Dest port, Sequence, Acknowledgment, Flags — interactive explorer
- **When to use which:** Video streaming (UDP), File download (TCP), VoIP (UDP), Banking (TCP)

#### Lesson 6.2: `tcp_connection.html` — اتصال TCP
- **Concept:** 3-Way Handshake (SYN, SYN-ACK, ACK), connection teardown (FIN, FIN-ACK, ACK)
- **Visualization:** **TCP timeline animator**
  - Two vertical timelines (Client | Server)
  - Animated arrows showing SYN, SYN-ACK, ACK
  - Color coded by state machine
- **Sequence numbers:** How data is ordered and reassembled
- **Wireshark output:** Real capture of a TCP handshake, explained line by line

#### Lesson 6.3: `flow_congestion.html` — التحكم في التدفق والازدحام
- **Concept:** Flow Control (Sliding Window, Stop-and-Wait), Congestion Control (Slow Start, AIMD)
- **Visualization:** **Sliding window visualizer**
  - See window size grow and shrink
  - Simulate packet loss → congestion window collapses
- **Analogy:** "الـ Sliding Window زي ما بتبعت رسائل — مش هتستنى رد على كل رسالة قبل ما تبعت التالية"
- **TCP Cubic / LFN challenge** — modern congestion algorithms overview

#### Lesson 6.4: `ports_sockets.html` — المنافذ والـ Sockets
- **Concept:** Port numbers (well-known 0-1023, registered 1024-49151, ephemeral)
- **Visualization:** **Port scanner simulator** — "scan" a virtual server, see which ports are open
- **Socket = IP + Port:** The 5-tuple that uniquely identifies a connection
- **Well-known ports:** 20/21 FTP, 22 SSH, 25 SMTP, 53 DNS, 80 HTTP, 443 HTTPS, 3306 MySQL
- **Socket programming intro:** Python snippet showing `socket.connect()`

---

### 🟠 UNIT 7: طبقة التطبيق — Application Layer
**Level:** Intermediate → Advanced | **Lessons:** 5 | **Color:** `#F97316` (Orange)

> *"كل حاجة بتشوفها على الشاشة — من المتصفح للإيميل — بتشتغل هنا"*

#### Lesson 7.1: `http_https.html` — HTTP والـ HTTPS
- **Concept:** HTTP request/response cycle, methods (GET, POST, PUT, DELETE, PATCH), status codes
- **Hook:** "كل مرة بتفتح موقع — بيحصل محادثة كاملة بين ُمتصفحك والـ Server. جوزهم مابيعرفوش بعض قبل كده"
- **Visualization:** **HTTP request inspector**
  - Enter a URL → simulated request/response displayed with headers
  - Status codes: 200 OK, 301 Redirect, 404 Not Found, 500 Server Error
- **HTTPS:** TLS handshake animation, certificates, encryption
- **HTTP/2 vs HTTP/3:** Multiplexing, QUIC protocol
- **DevTools tip:** كيف تشوف HTTP requests في المتصفح

#### Lesson 7.2: `dns.html` — نظام اسم النطاق DNS
- **Concept:** How DNS resolves names to IPs — recursive and iterative resolution
- **Hook:** "إنت مش بتكتب 142.250.80.68 عشان تفتح Google. إنت بتكتب google.com. ده بسبب الـ DNS."
- **Visualization:** **DNS resolution animator**
  - Type a domain → watch query go through: Local Cache → Root → TLD → Authoritative
  - Shows actual resolution steps with timing
- **Record types:** A, AAAA, CNAME, MX, NS, TXT, PTR — with real examples
- **DNS caching and TTL:** Why sometimes you still see old IP
- **Egyptian examples:** .eg domains, نظام DNS في مصر

#### Lesson 7.3: `email_protocols.html` — بروتوكولات البريد الإلكتروني
- **Concept:** SMTP (sending), POP3 vs IMAP (receiving), MIME (attachments)
- **Visualization:** **Email journey animator**
  - Compose email → SMTP to sender's server → DNS MX lookup → SMTP to recipient's server → IMAP/POP3 to client
- **SMTP commands:** EHLO, MAIL FROM, RCPT TO, DATA, QUIT — step by step
- **Spam and SPF/DKIM/DMARC:** How email authentication works

#### Lesson 7.4: `ftp_ssh.html` — FTP والـ SSH
- **Concept:** FTP (active vs passive modes), SFTP, SSH (key-based auth, tunneling)
- **Visualization:** FTP active vs passive connection compared — "ليه الـ Passive أحسن وراء الـ NAT"
- **SSH:** Public/private key — "الباب الذكي اللي بيفتح بمفتاحك بس"
- **Practical:** SSH commands, key generation, `scp`, port forwarding
- **Security note:** استخدام SFTP بدل FTP العادي

#### Lesson 7.5: `dhcp_snmp.html` — DHCP والـ SNMP
- **DHCP:** Deep dive into options, relay agents, DHCPNAK
- **SNMP:** Network management protocol — how Telecom Egypt monitors its network
- **Concept:** MIB (Management Information Base), OIDs, SNMP traps
- **Visualization:** SNMP monitoring dashboard simulation
- **NTP:** Time synchronization — "ليه كل الأجهزة محتاجة نفس الوقت بالظبط"

---

### 🌸 UNIT 8: أمن الشبكات — Network Security
**Level:** Advanced | **Lessons:** 5 | **Color:** `#EC4899` (Pink)

> *"كل شبكة بلا حماية هي دعوة مفتوحة للهاكرز"*

#### Lesson 8.1: `security_concepts.html` — مفاهيم الأمن
- **Concept:** CIA Triad (Confidentiality, Integrity, Availability), threats, vulnerabilities, attacks
- **Hook:** "في 2016 قرصنة شبكة Bangladesh Bank سرقت 81 مليون دولار! إزاي؟ كيف نمنع ده؟"
- **Threat types:** DoS/DDoS, MitM, Sniffing, Spoofing, Phishing
- **Visualization:** **Attack scenario simulator** — choose an attack, see how it works step by step
- **Defense layers:** Defense in Depth concept — multiple security layers
- **Egyptian context:** أهم الحوادث الأمنية اللي أثرت على المنطقة

#### Lesson 8.2: `cryptography.html` — التشفير
- **Concept:** Symmetric (AES) vs Asymmetric (RSA), hashing (SHA), PKI
- **Visualization:** **Encryption demo**
  - Type a message → see it encrypted (Caesar cipher for visualization, AES conceptually)
  - Key exchange visualization — Diffie-Hellman with paint mixing analogy
- **Analogy:** "التشفير المتماثل = نفس الكودة. التشفير غير المتماثل = قفل بمفتاحين مختلفين"
- **TLS/SSL:** How HTTPS actually works — certificate chain visualization
- **Hashing:** MD5 vs SHA256 — why MD5 is broken

#### Lesson 8.3: `firewalls_ids.html` — الجدران النارية والكشف عن التسلل
- **Concept:** Packet filter, Stateful firewall, Application firewall, IDS vs IPS
- **Visualization:** **Firewall rules simulator**
  - Define rules → send packets → see which are allowed/blocked
- **DMZ concept:** Three-zone network (Internet → DMZ → Internal)
- **IDS/IPS:** Signature-based vs anomaly-based detection
- **Egyptian context:** نظام الجدار الناري في شبكة الجامعة

#### Lesson 8.4: `vpn_tunneling.html` — الشبكات الخاصة الافتراضية VPN
- **Concept:** VPN types (Remote Access, Site-to-Site), protocols (IPSec, SSL/TLS, WireGuard)
- **Visualization:** **VPN tunnel animation** — packet encrypted, sent through tunnel, decrypted at other end
- **IPSec modes:** Transport vs Tunnel
- **Why VPN:** Privacy, bypassing geo-restrictions, Corporate access
- **Practical:** WireGuard config example

#### Lesson 8.5: `ethical_hacking.html` — الاختراق الأخلاقي
- **Concept:** Penetration testing phases, Kali Linux tools, responsible disclosure
- **Phases:** Reconnaissance → Scanning → Exploitation → Post-Exploitation → Reporting
- **Tools:**
  - `nmap` — port scanning visualization
  - `Wireshark` — packet capture demo
  - Metasploit — framework overview
- **Ethical note:** "كل اللي بنتعلمه ده للحماية والتعلم — مش للاختراق غير القانوني"
- **Bug bounty:** How to make money legally from security skills

---

### 🌿 UNIT 9: المهارات العملية — Practical Networking Skills
**Level:** Intermediate → Advanced | **Lessons:** 5 | **Color:** `#14B8A6` (Teal)

> *"النظرية بدون تطبيق مش بتوديك بعيد — الشبكة الحقيقية بتختلف عن الكتاب"*

#### Lesson 9.1: `cisco_cli.html` — Cisco IOS CLI أساسيات
- **Concept:** Router/Switch modes (User EXEC, Privileged EXEC, Global Config), basic commands
- **Visualization:** **Interactive Cisco terminal simulator**
  - Actual working CLI — type commands, get responses
  - Commands available: `show interfaces`, `show ip route`, `ping`, `traceroute`, `configure terminal`
  - Color-coded output (green = success, red = error)
- **Common commands cheat sheet:** Displayed alongside the terminal
- **Labs:** Configure a hostname, set passwords, basic interface config

#### Lesson 9.2: `packet_analysis.html` — تحليل الحزم (Wireshark)
- **Concept:** How to use Wireshark, reading captures, following streams
- **Visualization:** **Simulated Wireshark UI**
  - Pre-loaded packet captures (HTTP, DNS, TCP handshake)
  - Click a packet → see all fields decoded
  - Follow TCP stream → reconstruct HTTP conversation
- **Filters:** `tcp`, `http`, `ip.addr == 192.168.1.1`, `dns.qry.name`
- **Lab:** "هات الـ password اللي اتبعت على HTTP (مش HTTPS) من الـ capture ده"

#### Lesson 9.3: `network_troubleshooting.html` — استكشاف الأخطاء
- **Concept:** Systematic troubleshooting using OSI model (top-down vs bottom-up)
- **Tools:** `ping`, `traceroute`/`tracert`, `ipconfig`/`ifconfig`, `netstat`, `nslookup`, `arp -a`
- **Visualization:** **Troubleshooting wizard**
  - Simulate "لا يوجد اتصال بالإنترنت" — walk through diagnosis steps
  - Each step: what command to run + what output means
- **Methodology:** Physical → Link → Network → Transport → Application
- **Common problems:** "الإنترنت واقف/بطيء" diagnostic flowchart

#### Lesson 9.4: `network_design.html` — تصميم الشبكات
- **Concept:** Small office/home network, enterprise network, hierarchical design (Core, Distribution, Access)
- **Visualization:** **Network topology designer** (canvas-based)
  - Drag devices from palette onto canvas
  - Draw connections
  - Export as network diagram
- **Three-layer hierarchy:** Core (speed) → Distribution (policy) → Access (users)
- **Project:** "صمم شبكة لشركة متوسطة فيها 3 أقسام و200 موظف"

#### Lesson 9.5: `cloud_networking.html` — الشبكات السحابية
- **Concept:** VPC (Virtual Private Cloud), SD-WAN, CDN, load balancing
- **AWS/Azure networking:** Subnets, Security Groups, Route Tables, Internet Gateway
- **CDN:** "ليه Netflix بطيء في مصر أحياناً — وإزاي الـ CDN بيحل المشكلة دي"
- **Visualization:** CDN PoP map — request routing to nearest server
- **Egyptian context:** AWS Middle East (Bahrain), العمل على Cloud في الشركات المصرية

---

### 🏆 UNIT 10: المشروع النهائي والمسار المهني — Capstone & Career
**Level:** All Levels | **Lessons:** 4 | **Color:** `#D946EF` (Fuchsia)

> *"كل اللي فات كان تحضير — دلوقتي وقت الشغل الحقيقي"*

#### Lesson 10.1: `capstone_design.html` — مشروع: تصميم شبكة كاملة
- **Full project:** Design and build a complete enterprise network from requirements
- **Scenario:** شركة تقنية مصرية ناشئة — 3 مكاتب، 2 data centers، 500+ موظف
- **Steps:** Requirements → Physical topology → IP scheme → Routing → Security → Documentation
- **Deliverables:** Network diagram + IP address plan + Routing config + Security policy

#### Lesson 10.2: `capstone_analysis.html` — مشروع: تحليل الحركة
- **Full project:** Capture and analyze real network traffic, write a security report
- **Scenarios:** Find the malware C2 traffic, identify the slow application, audit the HTTP usage
- **Tools:** Simulated Wireshark captures → analysis questions
- **Report writing:** Professional network analysis report template

#### Lesson 10.3: `certifications.html` — شهادات الشبكات
- **Certification paths:**
  - Cisco: CCNA → CCNP → CCIE
  - CompTIA: Network+ → Security+
  - Juniper: JNCIA → JNCIS
  - Cloud: AWS Networking Specialty, Azure Network Engineer
- **Study resources:** What to use, how to study, practice labs
- **Egyptian market:** متوسط رواتب Network Engineers في مصر، شركات توظيف
- **CCNA prep:** Sample questions with detailed answers

#### Lesson 10.4: `career_guide.html` — المسار المهني
- **Career paths:** Network Engineer, Network Architect, NOC Engineer, Security Engineer, Cloud Network Engineer, SDN Engineer
- **Egyptian market salary ranges** per role
- **Skills matrix:** What you know now vs what to learn next
- **Portfolio:** How to document your networking projects for employers
- **Interview prep:** Top 30 networking interview questions with full answers

---

## 📁 Project Structure

```
network-mastery/
├── index.html                         # Main portal (10-unit grid) — RTL
├── README.md
├── css/
│   └── global-net.css                 # Global design system (adapted from global-db.css)
│
├── Unit1/                             # عالم الشبكات
│   ├── why_networks.html
│   ├── network_types.html
│   ├── network_topologies.html
│   ├── network_hardware.html
│   └── network_history.html
│
├── Unit2/                             # نماذج OSI وTCP/IP
│   ├── osi_model.html
│   ├── tcp_ip_model.html
│   ├── encapsulation.html
│   ├── protocols_intro.html
│   └── addressing_basics.html
│
├── Unit3/                             # الطبقة الفيزيائية
│   ├── transmission_media.html
│   ├── signal_encoding.html
│   ├── multiplexing.html
│   └── switching_transmission.html
│
├── Unit4/                             # طبقة الوصول للبيانات
│   ├── framing_error.html
│   ├── mac_addresses.html
│   ├── switching_vlans.html
│   ├── spanning_tree.html
│   └── wifi_wireless.html
│
├── Unit5/                             # طبقة الشبكة
│   ├── ip_addressing.html
│   ├── subnetting.html               # The most important lesson ⭐
│   ├── ipv6.html
│   ├── routing_basics.html
│   ├── routing_protocols.html
│   └── nat_dhcp.html
│
├── Unit6/                             # طبقة النقل
│   ├── tcp_udp.html
│   ├── tcp_connection.html
│   ├── flow_congestion.html
│   └── ports_sockets.html
│
├── Unit7/                             # طبقة التطبيق
│   ├── http_https.html
│   ├── dns.html
│   ├── email_protocols.html
│   ├── ftp_ssh.html
│   └── dhcp_snmp.html
│
├── Unit8/                             # أمن الشبكات
│   ├── security_concepts.html
│   ├── cryptography.html
│   ├── firewalls_ids.html
│   ├── vpn_tunneling.html
│   └── ethical_hacking.html
│
├── Unit9/                             # المهارات العملية
│   ├── cisco_cli.html
│   ├── packet_analysis.html
│   ├── network_troubleshooting.html
│   ├── network_design.html
│   └── cloud_networking.html
│
├── Unit10/                            # الكابستون والمسار
│   ├── capstone_design.html
│   ├── capstone_analysis.html
│   ├── certifications.html
│   └── career_guide.html
│
└── simulators/                        # Shared interactive simulators (JS modules)
    ├── packet-sim.js                  # Packet journey visualizer
    ├── subnet-calc.js                 # Subnetting calculator
    ├── cisco-terminal.js              # Cisco CLI emulator
    ├── topology-builder.js            # Network topology canvas
    └── wireshark-sim.js               # Packet capture simulator
```

**Total:** 10 Units | **43 Lessons** | **43+ Interactive Visualizations**

---

## 🔧 New Interactive Components Built Specifically for Networking

### 1. Packet Journey Visualizer (`simulators/packet-sim.js`)
- Choose source device and destination device on a canvas network
- Select protocol (HTTP, DNS, ICMP)
- Watch the packet travel hop-by-hop with:
  - Encapsulation/decapsulation at each layer shown
  - TTL decrement at each router
  - MAC address change at each router
  - Layer labels that animate

### 2. Subnetting Calculator (`simulators/subnet-calc.js`)
- Input: IP address + CIDR prefix (or subnet mask)
- Live output: Network, Broadcast, Host range, Total hosts, Wildcard mask
- Binary representation shown below each field
- "Split this network" mode: divide into N equal subnets with one click

### 3. Cisco Terminal Emulator (`simulators/cisco-terminal.js`)
- Realistic Cisco IOS prompt simulation
- Supports: `enable`, `configure terminal`, `show interfaces`, `show ip route`, `interface`, `ip address`, `no shutdown`, `ping`, `traceroute`, `show running-config`, `hostname`
- Color-coded output matching real IOS
- Help system (`?`) works
- Up-arrow command history

### 4. Network Topology Builder (`simulators/topology-builder.js`)
- Drag devices (Router, Switch, PC, Server, Firewall) from a palette
- Click-draw connections between devices
- Right-click device → configure IP address
- Calculate subnet automatically when you configure an interface
- Export as PNG

### 5. Wireshark Simulator (`simulators/wireshark-sim.js`)
- Pre-loaded packet captures: TCP handshake, DNS query, HTTP request
- Click any packet → see full decode tree (Ethernet → IP → TCP/UDP → Application)
- "Follow stream" → reassemble application data
- Filter bar (limited but functional): `tcp`, `udp`, `dns`, `http`, `icmp`, `ip.src==x.x.x.x`

### 6. OSI Layer Animator (inline, `osi_model.html`)
- 7 stacked visual layers
- Click a layer → expands with protocols, PDU name, devices, Arabic description
- "Send a message" mode → watch it pass through all layers with encapsulation

### 7. DNS Resolution Visualizer (inline, `dns.html`)
- Type a domain name → animated resolution:
  - Check local cache
  - Ask Root server (which TLD server to use)
  - Ask TLD server (.com, .eg)
  - Ask Authoritative server
  - Return IP, cache it
- Shows realistic timing and TTL values

---

## 📐 Alignment with Egyptian University Curricula

### Mapping to Forouzan (Data Communications and Networking) — Primary Egyptian textbook
| Textbook chapter | Platform Unit |
|---|---|
| Ch 1-2: Introduction & Models | Unit 1 + Unit 2 |
| Ch 3-4: Signals & Transmission | Unit 3.1 + 3.2 |
| Ch 6: Bandwidth Utilization | Unit 3.3 |
| Ch 11: Data Link Control | Unit 4.1 |
| Ch 14-15: Wired/Wireless LANs | Unit 4.2-4.5 |
| Ch 20: Network Layer: Internet | Unit 5 |
| Ch 23-24: Transport Layer | Unit 6 |
| Ch 25-30: Application Layer | Unit 7 |
| Ch 31-32: Network Security | Unit 8.1-8.4 |

### Also covers: Tanenbaum (Computer Networks)
- Ch 1: Introduction → Units 1-2
- Ch 2: Physical Layer → Unit 3
- Ch 3: Data Link Layer → Unit 4
- Ch 4: Network Layer → Unit 5
- Ch 6: Transport Layer → Unit 6
- Ch 7: Application Layer → Unit 7

### University Coverage
- ✅ FCIS Ain Shams — Computer Networks (CN) course
- ✅ FCAI Cairo University — Networks course
- ✅ GUC — Computer Networks
- ✅ AAST — Networking courses
- ✅ CCNA prep (Units 4-9 heavily aligned)

---

## 🧑‍💻 El Daheeh Content Examples for Network Mastery

### Hook for Unit 1 (`why_networks.html`)
```
🎬 [Scene opens on a server room with blinking lights]

"طيب... تخيل معايا دقيقة.

عندك موبايل فيه ألف صورة. عايز تبعتهم لأهلك في الإسكندرية.

قبل الشبكات — كنت هتعمل إيه؟

قرص فلوبي... يعني فلوبي على فلوبي على فلوبي... 😅

أو تسافر وتاخد الـ Laptop معاك.

بس اللي بيحصل دلوقتي؟ ضغطة واحدة من WhatsApp — وصت.

ده مش سحر. ده شبكة. وانت هتفهم كيف من الأول للآخر."
```

### Analogy for TCP 3-Way Handshake
```
"طيب الـ 3-Way Handshake ده إيه؟

تخيل إنت شايف حد في الشارع وعايز تكلمه.

أنت: (SYN) "ألو؟ تسمعني؟"

هو: (SYN-ACK) "آه سمعتك! وأنت تسمعني؟"

أنت: (ACK) "آه تمام، يلا نتكلم!"

كده الخط اتفتح. 

ده بالظبط اللي TCP بيعمله قبل ما يبعت أي بيانات.
مش هيبعت حاجة غير ما يتأكد إن الطرف الثاني موجود وعارف يرد."
```

### Analogy for DNS
```
"انت بتكتب 'google.com' في المتصفح.

المتصفح مش عارف 'google.com' ده فين.

بيبعت رسالة للـ DNS Server: 'Hey, google.com العنوان بتاعه إيه؟'

الـ DNS بيرد: '142.250.80.68'

المتصفح: 'شكراً!' — وبعدين بيتصل بالـ IP ده.

كده زي ما تتصل بحد ومعندكش رقمه — 
بتعمله بحث في الدليل التليفوني عشان تلاقي رقمه،
وبعدين بتتصل بيه."
```

---

## 🚀 Implementation Order

> [!TIP]
> Build in this exact order to always have a usable, impressive platform:

| Phase | What to Build | Priority |
|-------|--------------|----------|
| **Phase 1** | `index.html` (portal) + `css/global-net.css` | Foundation — the showcase |
| **Phase 2** | Unit 1 (5 lessons) | Onboarding — everyone starts here |
| **Phase 3** | Unit 2 (5 lessons) | OSI/TCP-IP — the mental model everything else builds on |
| **Phase 4** | Unit 5 (6 lessons) | Network Layer — most complex, most important |
| **Phase 5** | Unit 6 (4 lessons) | Transport Layer — TCP/UDP is essential |
| **Phase 6** | Unit 7 (5 lessons) | Application Layer — most relatable |
| **Phase 7** | Unit 4 (5 lessons) | Data Link — bridges theory to practice |
| **Phase 8** | Unit 3 (4 lessons) | Physical — foundational theory |
| **Phase 9** | Unit 8 (5 lessons) | Security — high-demand career skill |
| **Phase 10** | Unit 9 (5 lessons) | Practical Skills — hands-on capstone prep |
| **Phase 11** | Unit 10 (4 lessons) | Capstone + Career |
| **Phase 12** | Shared simulators (`simulators/`) | Polish and depth |

---

## 📊 Total Scope

| Metric | Count |
|--------|-------|
| **Total Units** | 10 |
| **Total Lessons** | 43 |
| **Interactive Visualizations** | 43+ (minimum 1 per lesson) |
| **Unique Simulators** | 7 (packet sim, CLI, topology, Wireshark sim, subnet calc, DNS viz, OSI anim) |
| **Quiz Questions** | 100+ |
| **El Daheeh Scripts** | 43 |
| **Subnetting Exercises** | 20+ |

---

## ✅ Verification Plan

### Per Lesson Checklist (replicate from DB Mastery)
- [ ] Fixed navbar with back button + section anchors
- [ ] Reading progress bar
- [ ] Hero section: badge (Unit N • Lesson N) + gradient h1 + Arabic subtitle + description
- [ ] At least 3 content sections alternating `.lesson-section` / `.lesson-section.alt-bg`
- [ ] Minimum 1 interactive visualization per lesson
- [ ] El Daheeh style Arabic text in `.rtl-block` containers
- [ ] English terms wrapped in `.english` spans
- [ ] At least 3 quiz questions with correct/wrong feedback
- [ ] Bottom navigation (prev/next lesson links)
- [ ] Reading progress JS (`window.addEventListener('scroll', ...)`)
- [ ] AOS animations initialized

### Portal Checklist
- [ ] RTL page (`lang="ar" dir="rtl"`)
- [ ] Particle canvas (cyan/blue hues for networking)
- [ ] 3 aurora glow blobs
- [ ] 10 unit cards with correct colors and lesson links
- [ ] Stats bar: 10 وحدات | 43 درس | 7 أدوات تفاعلية | 100+ تمرين
- [ ] Card tilt effect on mousemove
- [ ] All lesson anchor links verified

### Cross-browser Testing
- [ ] Chrome/Edge (primary)
- [ ] Firefox
- [ ] Mobile (320px, 375px) — single column layout
- [ ] Tablet (768px) — 2-column grid

---

## 📁 Project Location

```
d:\work\projects\network\
```

Sibling to: `d:\work\projects\database\`

---

> [!IMPORTANT]
> ## Ready to Build?
>
> This plan is **immediately executable** — every pattern is proven from the real Database Mastery codebase. The first step is:
>
> 1. Create `d:\work\projects\network\` directory
> 2. Copy `css/global-db.css` → `css/global-net.css` and update the unit color variables
> 3. Build `index.html` portal (clone structure from DB `index.html`, update colors + content)
> 4. Build Unit 1 Lesson 1: `why_networks.html` (the most important hook lesson)
>
> Say **"ابدأ الـ Phase 1"** to start building immediately.
