# PROPOSAL_CATALOG.md
<!-- PROPOSAL_CATALOG.md -->

> **Fuente:** `index.html` — web de posicionamiento personal (josegalindo.net)
> **Propósito:** inventario de referencia versionado de todo el contenido editorial de la página, en ES/EN, para facilitar su mantenimiento fuera del HTML/WordPress.
> **Idiomas cubiertos:** Español (ES, idioma por defecto) / Inglés (EN)
> **Estructura de la página:** Cabecera → Servicios Take Away → Pilares de Competencia → Certificaciones Profesionales → Footer
> **Última extracción:** 2026-09-11

---

## Índice

1. [Metadatos globales y CTAs](#1-metadatos-globales-y-ctas)
2. [Cabecera (Header)](#2-cabecera-header)
3. [Pilares de Competencia](#3-pilares-de-competencia)
4. [Certificaciones Profesionales](#4-certificaciones-profesionales)
5. [Footer](#5-footer)
6. [Notas técnicas de implementación (i18n)](#6-notas-técnicas-de-implementación-i18n)

---

## 1. Metadatos globales y CTAs

| Elemento | Valor |
|---|---|
| `<title>` / `page_title` | José Galindo IT Service Delivery & Governance Leader *(idéntico en ES y EN)* |
| Idioma por defecto | `es` (fallback si no hay preferencia guardada) |
| Selector de idioma | Botones `ES` / `EN` en la cabecera, arriba a la derecha |
| CTA "Agendar Cita" (`btn_book`) | ES: `🗓️ Agendar Cita` · EN: `🗓️ Book a Call` → enlaza a `https://cal.com/jose-galindo/30min` (target `_blank`) |
| CTA "Ver Competencias" (`btn_skills`) | ES: `Ver Competencias` · EN: `View Competencies` → ancla `#competencies` |
| CTA "Contactar" (`btn_contact`) | ES: `Contactar` · EN: `Contact Me` → ancla `#contact` (footer) |

---

## 2. Cabecera (Header)

| Clave i18n | ES | EN |
|---|---|---|
| `badge` | Estrategia & Operaciones IT | IT Strategy & Operations |
| `title` (H1) | IT Service Delivery & Governance Leader | IT Service Delivery & Governance Leader |
| `subtitle` | Liderando la transformación digital, la excelencia operativa e implementación de marcos de gobierno ITIL/COBIT para maximizar el valor de negocio. | Leading digital transformation, operational excellence, and the implementation of ITIL/COBIT governance frameworks to maximize business value. |

---

## 3. Pilares de Competencia

Sección ancla `id="competencies"`. Título de sección (`section_competencies`): ES *"Pilares de Competencia"* / EN *"Core Competencies"*.

Los **títulos de las 4 tarjetas y sus iconos son fijos** (no están en el sistema i18n, mismo texto en ES y EN). Las **descripciones** y **algunas tags** sí están traducidas.

### C1 — ⚙️ IT Governance & Compliance

| Campo | ES | EN |
|---|---|---|
| Descripción (`card1_desc`) | Diseño y aplicación de marcos de gobierno TI (COBIT, ISO 20000, ISO 21500, ISO 31000) que alinean la ejecución tecnológica con los objetivos de negocio, controlando presupuesto y riesgo en portfolios superiores a 200.000 horas de delivery. | Design and application of IT governance frameworks (COBIT, ISO 20000, ISO 21500, ISO 31000) aligning technology execution with business objectives, controlling budget and risk across portfolios exceeding 200K delivery hours. |
| Tags | `COBIT` · `ISO 21500` · Reporting a Comités (SteerCo) (`tag_repor`) · Gestión de Riesgos (ISO 31000) (`tag_risk`) · Audit (`tag_audit`) · Gobierno de Portfolio (PMO) (`tag_gover`) | `COBIT` · `ISO 21500` · SteerCo Reporting (`tag_repor`) · Risk Management (ISO 31000) (`tag_risk`) · IT Audit (`tag_audit`) · Portfolio Governance (`tag_gover`) |

### C2 — 📊 Service Delivery Excellence

| Campo | ES | EN |
|---|---|---|
| Descripción (`card2_desc`) | Gestión del ciclo de vida del servicio TI bajo ITIL® 4: definición y supervisión de SLAs, gestión de incidencias y problemas, y mejora continua (CSI) en cuentas multiproveedor de hasta 132.000 horas al año. | IT service lifecycle management under ITIL® 4: defining and monitoring SLAs, incident and problem management, and continuous service improvement (CSI) across multi-vendor accounts of up to 132K hours a year. |
| Tags (fijas, no traducidas) | `ITIL® v4` · ANS / KPI (`tag_sla`) · Gestión de Incidencias y Problemas (`tag_inc`) · `CSI` | `ITIL® v4` · SLA / KPI (`tag_sla`) · Incident & Problem Mgmt (`tag_inc`) · `CSI` |

### C3 — 🤝 Vendor & Stakeholder Management

| Campo | ES | EN |
|---|---|---|
| Descripción (`card3_desc`) | Gestión estratégica de proveedores tecnológicos (RFPs, negociación de tarifas y contratos, evaluación de rendimiento) y alineación con líderes del negocio, en entornos multiproveedor con P&L de hasta 6,5M€. | Strategic management of technology vendors (RFPs, rate and contract negotiation, performance evaluation) and alignment with business leaders across multi-vendor environments with P&L accountability up to €6.5M. |
| Tags | Gestión de Proveedores/Multiproveedor (`tag_vendor`)· Negociación de Tarifas y Contratos(`tag_neg`) · Presupuesto IT (P&L) (`tag_budget`) · `Stakeholders` | Vendor/Multi-vendor Management (`tag_vendor`) · Rate & Contract Negotiation (`tag_neg`) · IT Budget (P&L) (`tag_budget`) · `Stakeholders` |

### C4 — 🚀 Data Platform & Regulatory Delivery

| Campo | ES | EN |
|---|---|---|
| Descripción (`card4_desc`) | Delivery técnico de plataformas de datos (Data Warehouse, Big Data) y programas regulatorios (BCBS 239, IAS 39), gobernando SDLC, Release Management y control de calidad en modelos multifactoría. | Technical delivery of data platforms (Data Warehouse, Big Data) and regulatory programs (BCBS 239, IAS 39), governing SDLC, Release Management and quality control across multi-factory models |
| Tags | Plataforma Informacional (`tag_data`) · Gestión de Entregables y Releases (`tag_sdlc`) · Reporting Regulatorio (BCBS 239) (`tag_rereg`) · Delivery Multiproveedor (`tag_delm`) | Data Warehousing / Big Data (`tag_data`) · SDLC & Release Management (`tag_sdlc`) · Regulatory Reporting (BCBS 239) (`tag_rereg`) · Multi-vendor Delivery (`tag_delm`) |

### C5 — 🚀 Digital Transformation & DevOps

| Campo | ES | EN |
|---|---|---|
| Descripción (`card5_desc`) | Coordinación de metodologías ágiles e híbridas (Scrum, Kanban, Lean IT) y adopción de prácticas DevOps/CI-CD a nivel de gobierno del delivery, reduciendo hasta un 65% la tasa de fallos en cambios (CFR). | Coordination of agile and hybrid methodologies (Scrum, Kanban, Lean IT) and governance-level adoption of DevOps/CI-CD practices, cutting change failure rate (CFR) by up to 65%. |
| Tags (fijas, no traducidas) | `Agile / Scrum` · `Lean IT` · `DevOps / CI-CD` · Gestión de Cambios TI (`tag_chm`) | `Agile / Scrum` · `Lean IT` · `DevOps / CI-CD` · IT Change Management (`tag_chm`) |

### C6 — 🚀 Digital Transformation & DevOps

| Campo | ES | EN |
|---|---|---|
| Descripción (`card6_desc`) | Liderazgo de equipos multidisciplinares en entornos híbridos y cloud, fomentando culturas DevOps, agilidad y optimización de costes (FinOps). | Leadership of multidisciplinary teams in hybrid and cloud environments, fostering DevOps cultures, agility, and cost optimization (FinOps). |
| Tags (fijas, no traducidas) | `Agile / Scrum` · `Cloud Operations` · `DevOps Culture` · `FinOps` | `Agile / Scrum` · `Cloud Operations` · `DevOps Culture` · `FinOps` |
---

## 4. Certificaciones Profesionales

Título de sección (`section_certs`): ES *"Certificaciones Profesionales"* / EN *"Professional Certifications"*.
El contenido de las tarjetas **no está traducido** (mismo texto en ambos idiomas):

| Certificación | Entidad emisora | Obtenida | 
|---|---|
| ITIL 4 Managing Professional | AXELOS Global Best Practice | 12/2025 |
| COBIT 2019 Foundation | ISACA | - |
| PMP® - Project Management Professional | Project Management Institute | 03/2026 |
| CRISC - Risk and Information Systems Control | ISACA | - |

---

## 5. Footer

- Ancla: `id="contact"`
- Texto (fijo, no traducido, con año dinámico calculado por JS `new Date().getFullYear()`):
  `© {año actual} - José Galindo IT Service Delivery & Governance Leader. All rights reserved.`

---

## 6. Notas técnicas de implementación (i18n)

Para quien mantenga el contenido (o migre a WordPress/otro CMS), conviene conservar estos comportamientos:

- **Mecanismo:** objeto JS `translations = { es: {...}, en: {...} }`; cada elemento traducible lleva un atributo `data-i18n="clave"`. La función `setLanguage(lang)` recorre todos los `[data-i18n]` y sustituye `innerHTML` (en `P`, `SPAN`, `DIV`, `H3`, `STRONG`, `H1`, `H2`, `A`) o `textContent` (resto de tags) según la clave.
- **Persistencia de idioma:** `localStorage.setItem('preferredLang', lang)`; al cargar la página, `localStorage.getItem('preferredLang') || 'es'` decide el idioma inicial. *(Nota: en un contexto de artefacto/vista previa sin `localStorage` persistente esto haría fallback silencioso a `'es'` cada carga; en el hosting real de la web sí persiste.)*
- **HTML embebido en cadenas de traducción:** `s3_evi` usa `<strong>` y `<br><br>` dentro del valor de la clave para diferenciar "General" de "Variante Data" en la misma celda de evidencia — es contenido con marcado, no texto plano.
- **Elementos NO traducidos (idénticos en ES/EN)** — mantener fuera del sistema i18n si se replica esta arquitectura:
  - Títulos e iconos de las 4 tarjetas de Pilares de Competencia.
  - Tags fijas: `COBIT`, `ISO 27001`, `ITIL v4`, `SLAs / KPIs`, `Incident & Problem Mgmt`, `CSI`, `Vendor Mgmt`, `Stakeholders`, `Agile / Scrum`, `Cloud Operations`, `DevOps Culture`, `FinOps`.
  - Badges de categoría de servicio: `PM`, `PM / Data`, `PM (SDM)`, `Data`.
  - Las 4 certificaciones (nombre + entidad emisora).
  - Texto del footer (excepto el año, calculado dinámicamente).
- **Anclas de navegación:** `#competencies` (inicio de Pilares de Competencia), `#contact` (footer).
- **CTA externo:** `https://cal.com/jose-galindo/30min` (único enlace externo de la página, abre en pestaña nueva).

---

## 8. Control de cambios de este catálogo

| Fecha | Cambio |
|---|---|
| 2026-09-11 | Primera extracción completa desde `index.html` (versión con 6 pilares de competencia, 4 certificaciones, i18n ES/EN). |

> Este fichero es una **referencia versionada**, no la fuente de renderizado de la web. Si el contenido de `index.html` cambia, actualiza primero el HTML y después sincroniza este documento (o a la inversa, si este documento pasa a ser la fuente editorial y el HTML se regenera desde aquí).
---
<!-- <EOF> PROPOSAL_CATALOG.md -->