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
| Descripción (`card1_desc`) | Diseño e implementación de marcos de gobierno alineados con COBIT, ISO 27001 e ISO 20000 para garantizar la alineación estratégica y gestión del riesgo. | Design and implementation of governance frameworks aligned with COBIT, ISO 27001, and ISO 20000 to ensure strategic alignment and risk management. |
| Tags | `COBIT` · `ISO 27001` · Gestión de Riesgos (`tag_risk`) · Auditoría IT (`tag_audit`) | `COBIT` · `ISO 27001` · Risk Management (`tag_risk`) · IT Audit (`tag_audit`) |

### C2 — 📊 Service Delivery Excellence

| Campo | ES | EN |
|---|---|---|
| Descripción (`card2_desc`) | Gestión del ciclo de vida del servicio TI basado en ITIL v4. Definición y supervisión de SLAs/OLAs, gestión de incidentes críticos y mejora continua (CSI). | IT service lifecycle management based on ITIL v4. Definition and monitoring of SLAs/OLAs, critical incident management, and continuous service improvement (CSI). |
| Tags (fijas, no traducidas) | `ITIL v4` · `SLAs / KPIs` · `Incident & Problem Mgmt` · `CSI` | `ITIL v4` · `SLAs / KPIs` · `Incident & Problem Mgmt` · `CSI` |

### C3 — 🤝 Vendor & Stakeholder Management

| Campo | ES | EN |
|---|---|---|
| Descripción (`card3_desc`) | Gestión estratégica de proveedores tecnológicos (RFPs, negociación de contratos, evaluación de rendimiento) y alineación con líderes del negocio. | Strategic management of technology vendors (RFPs, contract negotiation, performance evaluation) and alignment with business leaders. |
| Tags | `Vendor Mgmt` · Negociación (`tag_neg`) · Presupuesto IT (`tag_budget`) · `Stakeholders` | `Vendor Mgmt` · Negotiation (`tag_neg`) · IT Budget (`tag_budget`) · `Stakeholders` |

### C4 — 🚀 Digital Transformation & DevOps

| Campo | ES | EN |
|---|---|---|
| Descripción (`card4_desc`) | Liderazgo de equipos multidisciplinares en entornos híbridos y cloud, fomentando culturas DevOps, agilidad y optimización de costes (FinOps). | Leadership of multidisciplinary teams in hybrid and cloud environments, fostering DevOps cultures, agility, and cost optimization (FinOps). |
| Tags (fijas, no traducidas) | `Agile / Scrum` · `Cloud Operations` · `DevOps Culture` · `FinOps` | `Agile / Scrum` · `Cloud Operations` · `DevOps Culture` · `FinOps` |

---

## 4. Certificaciones Profesionales

Título de sección (`section_certs`): ES *"Certificaciones Profesionales"* / EN *"Professional Certifications"*.
El contenido de las tarjetas **no está traducido** (mismo texto en ambos idiomas):

| Certificación | Entidad emisora |
|---|---|
| ITIL 4 Managing Professional | AXELOS Global Best Practice |
| COBIT 2019 Foundation | ISACA |
| PMP® - Project Management Professional | Project Management Institute |
| CRISC - Risk and Information Systems Control | ISACA |

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
| 2026-09-11 | Primera extracción completa desde `index.html` (versión con 4 pilares de competencia, 4 certificaciones, i18n ES/EN). |

> Este fichero es una **referencia versionada**, no la fuente de renderizado de la web. Si el contenido de `index.html` cambia, actualiza primero el HTML y después sincroniza este documento (o a la inversa, si este documento pasa a ser la fuente editorial y el HTML se regenera desde aquí).
---
<!-- <EOF> PROPOSAL_CATALOG.md -->