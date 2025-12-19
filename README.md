# Monitor de Integridad de Datos: Honduras 2025
### Auditoría Técnica de Series Temporales - JSON Público CNE

Este repositorio documenta un ejercicio de auditoría ciudadana independiente sobre el proceso electoral 2025 en Honduras. El objetivo principal es asegurar la trazabilidad, transparencia y consistencia de los datos oficiales publicados por el Consejo Nacional Electoral (CNE) mediante el análisis de su fuente digital original.

## Estado del Monitoreo
El análisis se realiza de forma continua sobre el flujo de datos del sistema de resultados, enfocándose en los siguientes puntos críticos:

* **Seguimiento de Tendencias:** Evaluación de la estabilidad de la muestra procesada y su representatividad estadística conforme avanza el escrutinio.
* **Proyección de Irreversibilidad:** Análisis matemático basado en el volumen de actas pendientes para determinar la solidez de las tendencias actuales bajo condiciones de flujo orgánico.
* **Vigilancia de Actas Especiales:** Monitoreo específico del procesamiento de actas bajo escrutinio especial para verificar que su comportamiento aritmético sea consistente con la muestra general y no presente sesgos de manipulación manual.

## Metodología Técnica (Análisis de Series Temporales)
La auditoría se basa en la trazabilidad del dato mediante el **Análisis de Diferenciales Horarios (Delta Analysis)**. Este método permite identificar cambios en la base de datos que no son visibles en los totales acumulados.

### 1. Cálculo del Diferencial (Δ)
Para cada actualización del JSON oficial, se aplica la siguiente fórmula por cada candidato o fuerza política:

$$Δ = V_{n} - V_{n-1}$$

Donde $V_{n}$ es el total de votos en la captura actual y $V_{n-1}$ es el total en la captura inmediata anterior. En un sistema de conteo aditivo real, el valor de $Δ$ debe ser siempre mayor o igual a cero ($Δ \ge 0$). Un valor negativo indica la eliminación de registros en la base de datos.

### 2. Detección de Anomalías (Tabla de Control)
Esta tabla ilustra cómo el análisis diferencial identifica irregularidades técnicas que pasan desapercibidas en el total acumulado:

| Timestamp | Candidato A (Total) | Candidato B (Total) | Δ A (Votos Nuevos) | Δ B (Votos Nuevos) | Estado |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 22:00 | 150,000 | 140,000 | - | - | Base de control |
| 23:00 | 155,000 | 142,000 | +5,000 | +2,000 | **Normal** |
| 00:00 | **154,500** | 148,000 | **-500** | +6,000 | **ANOMALÍA** (Votos restados) |
| 01:00 | 156,000 | **165,000** | +1,500 | **+17,000** | **ALERTA** (Inyección atípica) |

### 3. Pruebas de Distribución y Validaciones
* **Análisis de Flujo:** Se compara el peso relativo del crecimiento de cada partido contra su tendencia histórica para detectar inyecciones de datos no orgánicas.
* **Integridad de Fuente:** Verificación de metadatos en el JSON para detectar reemplazos de actas o cambios en la información post-transmisión.

## Organización del Repositorio
* `/data`: Registro histórico de archivos JSON originales (fuente primaria con marca de tiempo).
* `/scripts`: Herramientas de código abierto (Python/Pandas) para la validación automática de datos.
* `/reports`: Documentación técnica de discrepancias identificadas, incluyendo logs de errores y comparativas de integridad.

---
**Aviso de Neutralidad:** Este proyecto es una iniciativa de transparencia técnica. No tiene afiliación partidaria y su propósito es proporcionar evidencia basada en datos para el fortalecimiento de la integridad electoral.
