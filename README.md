# ES: Monitor de Integridad de Datos: Honduras 2025
## Auditoría Técnica de Series Temporales - JSON Público CNE

Este repositorio documenta una auditoría ciudadana independiente sobre el proceso electoral 2025 en Honduras. El objetivo es asegurar la trazabilidad y consistencia de los datos oficiales publicados por el Consejo Nacional Electoral (CNE).

---

## Hallazgos Críticos
El análisis forense realizado sobre la serie histórica de datos (ubicada en `/data`) ha identificado las siguientes irregularidades:

* **Interrupción de Transparencia (Data Blackout):** Suspensión de la divulgación de resultados nominales el 08/12 entre las 14:00 y 17:00, periodo en el cual se detectó un cambio de tendencia estadísticamente improbable.
* **Manipulación del Universo:** Alteración del conteo total de actas proyectadas (+15 actas) sin justificación técnica durante el procesamiento.
* **Parálisis del Sistema:** Estancamiento deliberado del flujo de datos al alcanzar el 99.4%, manteniendo 2,773 actas en estado de "inconsistencia" (14.4% del total).

**[LEA EL REPORTE FORENSE COMPLETO AQUÍ](./reports/FORENSIC_TIMELINE_HN2025.md)**

---

## Expediente de Evidencia

Para garantizar la inmutabilidad de la prueba, se han organizado los registros en las siguientes secciones:

### 1. [Predicciones y Cronología (07/12)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/tree/main/evidence/evidence/predictions-chronology)
**Prueba reina de intencionalidad.** Registro de alertas técnicas y OSINT emitidas **24 horas antes** de la caída del sistema, donde se predijeron con exactitud los patrones de manipulación que el CNE/PNH ejecutaría posteriormente.

### 2. [Ingeniería Social y Censura (Shadowban)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/tree/main/evidence/social-engineering)
Documentación de la actividad coordinada (cuentas de choque) para desacreditar la auditoría y la ejecución de restricciones técnicas (Shadowban) en redes sociales tras la divulgación de los hallazgos del 99.4%.

### 3. [Mapa de Evidencia (Capturas Crudas)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/blob/main/EVIDENCE_MAP.md)
Relación directa entre archivos locales y publicaciones originales. Incluye borrados masivos de actas y saltos estadísticos imposibles de revertir sin manipulación.

---

## Organización del Repositorio
* **/data**: Archivos JSON originales (Raw snapshots) extraídos directamente de la API del CNE. Cada archivo incluye su marca de tiempo original.
* **/reports**: Documentación técnica, análisis de discrepancias identificadas y timeline forense.
* **/evidence**: Capturas de pantalla, registros de OSINT y documentación de ataques de ingeniería social.

## Verificación de Integridad
Cada archivo en `/data` cuenta con un Hash SHA-256 para garantizar que la evidencia no ha sido modificada post-descarga. Puede verificar la integridad de los datos ejecutando:
`Get-FileHash data/*.json` (PowerShell) o `sha256sum data/*.json` (Linux).

## Aviso de Neutralidad
Este repositorio es una iniciativa técnica independiente y no partidista. Su único propósito es proporcionar evidencia basada en datos sobre la integridad del proceso electoral de Honduras 2025. Todos los hallazgos se derivan estrictamente de los datos JSON oficiales.

---

# EN: Data Integrity Monitor: Honduras 2025
## Technical Time-Series Audit - CNE Public JSON

This repository documents an independent citizen audit of the 2025 electoral process in Honduras. The goal is to ensure the traceability and consistency of the official data published by the National Electoral Council (CNE).

---

## Critical Findings
Forensic analysis performed on the historical data series (located in `/data`) has identified the following irregularities:

* **Transparency Interruption (Data Blackout):** Suspension of the disclosure of nominal results on 12/08 between 14:00 and 17:00, a period in which a statistically improbable trend shift was detected.
* **Universe Manipulation:** Alteration of the total projected tally sheet count (+15 sheets) without technical justification during processing.
* **System Paralysis:** Deliberate stagnation of the data flow upon reaching 99.4%, keeping 2,773 tally sheets in an "inconsistency" state (14.4% of the total).

**[READ THE FULL FORENSIC REPORT HERE](./reports/FORENSIC_TIMELINE_HN2025.md)**

---

## Evidence Dossier

To guarantee the immutability of the proof, records have been organized into the following sections:

### 1. [Predictions and Chronology (12/07)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/tree/main/evidence/evidence/predictions-chronology)
**Primary evidence of intent.** Record of technical and OSINT alerts issued **24 hours before** the system crash, where the manipulation patterns that the CNE/PNH would later execute were accurately predicted.

### 2. [Social Engineering and Censorship (Shadowban)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/tree/main/evidence/social-engineering)
Documentation of coordinated activity (shock accounts) to discredit the audit and the execution of technical restrictions (Shadowban) on social media following the disclosure of the 99.4% findings.

### 3. [Evidence Map (Raw Screenshots)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/blob/main/EVIDENCE_MAP.md)
Direct relationship between local files and original publications. Includes massive deletions of tally sheets and statistical jumps impossible to reverse without manipulation.

---

## Repository Structure
* **/data**: Original JSON files (Raw snapshots) extracted directly from the CNE API. Each file includes its original timestamp.
* **/reports**: Technical documentation, analysis of identified discrepancies, and forensic timeline.
* **/evidence**: Screenshots, OSINT records, and documentation of social engineering attacks.

## Integrity Verification
Each file in `/data` has a SHA-256 Hash to guarantee that the evidence has not been modified post-download. You can verify data integrity by running:
`Get-FileHash data/*.json` (PowerShell) or `sha256sum data/*.json` (Linux).

## Neutrality Disclosure
This repository is an independent, non-partisan technical initiative. Its sole purpose is to provide data-driven evidence regarding the integrity of the 2025 Honduran electoral process. All findings are derived strictly from the official JSON data.
