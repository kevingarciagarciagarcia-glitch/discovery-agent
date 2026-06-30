# Requisitos Candidatos — Lecplast

## Funcionales

- **[R-01]** El sistema debe alertar al operador de extrusión cuando el peso acumulado del rollo en curso se aproxima al límite de la orden de producción.
  - Tipo: funcional
  - Origen: ESTRUSOR.md · Operador de extrusión (control-peso-rollo)

- **[R-02]** El sistema debe registrar el peso bruto, el peso neto y el peso del canuto de cada rollo producido durante el turno de extrusión.
  - Tipo: funcional
  - Origen: ESTRUSOR.md · Operador de extrusión (reporte-manual-extrusión)

- **[R-03]** El sistema debe generar el reporte de cierre de turno del operador de extrusión con el total de kilos producidos y kilos de merma.
  - Tipo: funcional
  - Origen: ESTRUSOR.md · Operador de extrusión (reporte-manual-extrusión)

- **[R-04]** El sistema debe validar automáticamente el balance de materiales del turno (kilos de resina despachados por bodega vs. kilos de producto + merma) y señalar discrepancias.
  - Tipo: funcional
  - Origen: ESTRUSOR.md · Operador de extrusión (discrepancia-kilos-resina)

- **[R-05]** El sistema debe registrar el consumo y la devolución de tintas (por color) y solventes durante el turno de impresión.
  - Tipo: funcional
  - Origen: IMPRESOR.md · Operador de impresión (reporte-tintas-solventes)

- **[R-06]** El sistema debe generar el reporte de cierre de turno del operador de impresión con el balance de tintas, solventes y rollos procesados.
  - Tipo: funcional
  - Origen: IMPRESOR.md · Operador de impresión (reporte-tintas-solventes)

- **[R-07]** El sistema debe llevar un conteo de bolsas producidas durante el turno de sellado, diferenciando unidades buenas de defectuosas.
  - Tipo: funcional
  - Origen: SELLADOR.md · Operador de sellado (contador-digital-impreciso, conteo-manual-bolsas)

- **[R-08]** El sistema debe generar el reporte de cierre de turno del operador de sellado con el balance de kilos de rollo entrados, bolsas buenas empacadas y kilos de merma.
  - Tipo: funcional
  - Origen: SELLADOR.md · Operador de sellado (reporte-manual-sellado)

- **[R-09]** El sistema debe permitir registrar incidencias de producción (rotura de burbuja, parada por estática, cambio de diseño) con marca de tiempo durante el turno.
  - Tipo: funcional
  - Origen: ESTRUSOR.md, SELLADOR.md · Operadores de extrusión y sellado

## No funcionales

- **[R-10]** La interfaz del operador debe poder usarse sin teclado en el flujo principal (pantalla táctil o controles físicos grandes), tolerante a manos sucias o con guantes.
  - Tipo: no funcional
  - Origen: ESTRUSOR.md, IMPRESOR.md, SELLADOR.md · Todos los operadores (contexto de trabajo físico en planta)

- **[R-11]** El sistema debe estar disponible durante todo el turno de producción (disponibilidad ≥ 99 % en horario de planta).
  - Tipo: no funcional
  - Origen: ESTRUSOR.md, SELLADOR.md · Todos los operadores (una caída detiene el registro)

- **[R-12]** El registro de datos de producción debe poder realizarse en tiempo real sin detener el flujo de la máquina.
  - Tipo: no funcional
  - Origen: ESTRUSOR.md, IMPRESOR.md, SELLADOR.md · Todos los operadores
