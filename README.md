# Monitor de Integridad de Datos: Honduras 2025
### Auditoría Técnica de Series Temporales - JSON Público CNE
### Technical Audit of Time Series Data - CNE Public JSON

Este repositorio documenta un ejercicio de auditoría ciudadana independiente sobre el proceso electoral 2025 en Honduras. El objetivo es asegurar la trazabilidad y consistencia de los datos oficiales publicados por el Consejo Nacional Electoral (CNE).

This repository documents an independent citizen audit of the 2025 Honduran electoral process. The main goal is to ensure the traceability and consistency of the official data published by the National Electoral Council (CNE).

## Estado del Monitoreo / Monitoring Status
El análisis se realiza de forma continua sobre el flujo de datos del sistema de resultados:

* **Seguimiento de Tendencias / Trend Tracking:** Evaluación de la estabilidad de la muestra y su representatividad estadística.
* **Proyección de Irreversibilidad / Irreversibility Projection:** Análisis matemático sobre el volumen de actas pendientes para determinar la solidez de las tendencias actuales.
* **Vigilancia de Actas Especiales / Special Scrutiny Watch:** Monitoreo específico del flujo de "Actas Especiales" (votos sujetos a escrutinio manual por inconsistencias en la transmisión inicial) para verificar su consistencia con la muestra general.

## Metodología Técnica / Technical Methodology
La auditoría se basa en el **Análisis de Diferenciales Horarios (Delta Analysis)**. / The audit is based on **Time-Series Delta Analysis**.

### 1. Cálculo del Diferencial (Δ) / Delta Calculation
$$Δ = V_{n} - V_{n-1}$$
* **ES:** Un valor negativo ($Δ < 0$) indica eliminación de registros en la base de datos oficial (imposibilidad física en un conteo aditivo).
* **EN:** A negative value ($Δ < 0$) indicates the deletion of records from the official database (a physical impossibility in an additive count).

### 2. Tabla de Control de Anomalías / Anomaly Control Table (Example)
| Timestamp | Cand. A (Total) | Cand. B (Total) | Δ A (Votos) | Δ B (Votos) | Estado / Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 22:00 | 150,000 | 140,000 | - | - | Base |
| 23:00 | 155,000 | 142,000 | +5,000 | +2,000 | **Normal** |
| 00:00 | **154,500** | 148,000 | **-500** | +6,000 | **ANOMALÍA** |
| 01:00 | 156,000 | **165,000** | +1,500 | **+17,000** | **ALERTA** |

## Fuentes y Verificación / Sources and Verification
* **Source URL:** `https://resultados2025.cne.hn/` (O la URL oficial correspondiente).
* **Data Integrity:** Cada archivo en `/data` incluye su respectivo Hash SHA-256 para garantizar que el archivo no ha sido modificado post-descarga.

## Organización / Structure
* `/data`: Archivos JSON originales (Raw snapshots).
* `/scripts`: Herramientas de validación (Python/Pandas).
* `/reports`: Documentación técnica de discrepancias identificadas.

---

### Neutrality Disclosure / Aviso de Neutralidad
**English:** This repository is an independent, non-partisan technical initiative. Its sole purpose is to provide data-driven evidence regarding the integrity of the 2025 Honduran electoral process. All findings are derived strictly from the official JSON data published by the National Electoral Council (CNE).

**Español:** Este repositorio es una iniciativa técnica independiente y no partidista. Su único propósito es proporcionar evidencia basada en datos sobre la integridad del proceso electoral de Honduras 2025. Todos los hallazgos se derivan estrictamente de los datos JSON oficiales publicados por el Consejo Nacional Electoral (CNE).
