# Monitor de Integridad de Datos: Honduras 2025
## Auditoría Técnica de Series Temporales - JSON Público CNE

Este repositorio documenta una auditoría ciudadana independiente sobre el proceso electoral 2025 en Honduras. El objetivo es asegurar la trazabilidad y consistencia de los datos oficiales publicados por el Consejo Nacional Electoral (CNE).

---

## Hallazgos Críticos / Critical Findings
El análisis forense realizado sobre la serie histórica de datos (ubicada en `/data`) ha identificado las siguientes irregularidades:

* **Interrupción de Transparencia (Data Blackout):** Suspensión de la divulgación de resultados nominales el 08/12 entre las 14:00 y 17:00, periodo en el cual se detectó un cambio de tendencia estadísticamente improbable.
* **Manipulación del Universo:** Alteración del conteo total de actas proyectadas (+15 actas) sin justificación técnica durante el procesamiento.
* **Parálisis del Sistema:** Estancamiento deliberado del flujo de datos al alcanzar el 99.4%, manteniendo 2,773 actas en estado de "inconsistencia" (14.4% del total).

**[LEA EL REPORTE FORENSE COMPLETO AQUÍ / READ THE FULL FORENSIC REPORT HERE](./reports/FORENSIC_TIMELINE_HN2025.md)**

---

## Expediente de Evidencia / Evidence Dossier

Para garantizar la inmutabilidad de la prueba, se han organizado los registros en las siguientes secciones:

### 1. [Predicciones y Cronología (07/12)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/tree/main/evidence/evidence/predictions-chronology)
**Prueba reina de intencionalidad.** Registro de alertas técnicas y OSINT emitidas **24 horas antes** de la caída del sistema, donde se predijeron con exactitud los patrones de manipulación que el CNE/PNH ejecutaría posteriormente.

### 2. [Ingeniería Social y Censura (Shadowban)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/tree/main/evidence/social-engineering)
Documentación de la actividad coordinada (cuentas de choque) para desacreditar la auditoría y la ejecución de restricciones técnicas (Shadowban) en redes sociales tras la divulgación de los hallazgos del 99.4%.

### 3. [Mapa de Evidencia (Capturas Crudas)](https://github.com/userf8a2c4/hnd-electoral-audit-2025/blob/main/EVIDENCE_MAP.md)
Relación directa entre archivos locales y publicaciones originales. Incluye borrados masivos de actas y saltos estadísticos imposibles de revertir sin manipulación.

---

## Organización del Repositorio / Structure
* **/data**: Archivos JSON originales (Raw snapshots) extraídos directamente de la API del CNE. Cada archivo incluye su marca de tiempo original.
* **/reports**: Documentación técnica bilingüe, análisis de discrepancias identificadas y timeline forense.
* **/evidence**: Capturas de pantalla, registros de OSINT y documentación de ataques de ingeniería social.

## Verificación de Integridad / Integrity Verification
Cada archivo en `/data` cuenta con un Hash SHA-256 para garantizar que la evidencia no ha sido modificada post-descarga. Puede verificar la integridad de los datos ejecutando:
`Get-FileHash data/*.json` (PowerShell) o `sha256sum data/*.json` (Linux).

## Neutrality Disclosure / Aviso de Neutralidad
**English:** This repository is an independent, non-partisan technical initiative. Its sole purpose is to provide data-driven evidence regarding the integrity of the 2025 Honduran electoral process. All findings are derived strictly from the official JSON data.

**Español:** Este repositorio es una iniciativa técnica independiente y no partidista. Su único propósito es proporcionar evidencia basada en datos sobre la integridad del proceso electoral de Honduras 2025. Todos los hallazgos se derivan estrictamente de los datos JSON oficiales.
