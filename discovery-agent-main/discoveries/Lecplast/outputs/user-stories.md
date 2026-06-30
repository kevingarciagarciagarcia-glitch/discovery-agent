# User Stories — Lecplast

> Núcleo del MVP: eliminar el cierre de turno manual. Las historias cubren los
> tres roles con respaldo de primera mano (ESTRUSOR.md, IMPRESOR.md, SELLADOR.md).
> Los dolores de calidad de proceso (calibre, viscosidad, desperdicio de arranque)
> quedan fuera de alcance por ahora: no tienen palanca de software directa.

---

## Operador de extrusión

- **[US-01]** Como operador de extrusión, quiero recibir una alerta cuando el peso del rollo en curso se acerque al límite de la orden de producción, para poder cortar a tiempo sin pasarme de kilos.
  - Criterios de aceptación:
    - Dado que el operador registró el inicio de un rollo con el peso objetivo, cuando el peso acumulado alcanza el 90 % del límite, entonces el sistema muestra una alerta visual clara en pantalla.
    - Dado que el peso supera el límite de la orden, entonces el sistema registra la desviación en kilogramos y la incluye en el reporte de cierre.
  - Fuente: ESTRUSOR.md

- **[US-02]** Como operador de extrusión, quiero registrar el peso bruto y el peso del canuto de cada rollo al terminarlo, para que el sistema calcule el peso neto y el total del turno sin que yo tenga que sumar a mano.
  - Criterios de aceptación:
    - Dado que el operador ingresa peso bruto y peso del canuto, cuando confirma el registro, entonces el sistema calcula el peso neto (bruto − canuto) y lo acumula al total del turno.
    - Dado que hay varios rollos registrados, entonces el sistema muestra el total acumulado de kilos netos y kilos de merma en todo momento.
  - Fuente: ESTRUSOR.md

- **[US-03]** Como operador de extrusión, quiero que el sistema compare los kilos de resina que me despachó bodega con los kilos que produje más la merma, para saber si el balance cuadra antes de presentar la hoja al supervisor.
  - Criterios de aceptación:
    - Dado que el operador registró los sacos de resina recibidos al inicio del turno, cuando solicita el cierre, entonces el sistema calcula la diferencia entre kilos de resina y (kilos producidos + merma) y la muestra.
    - Dado que hay una discrepancia mayor a cero, entonces el sistema la resalta con el valor exacto de la diferencia para que el operador la justifique antes de cerrar.
  - Fuente: ESTRUSOR.md

- **[US-04]** Como operador de extrusión, quiero generar el reporte de cierre de turno desde el sistema con un toque, para salir sin retrasos y sin que el supervisor me bloquee la salida por un error aritmético.
  - Criterios de aceptación:
    - Dado que hay al menos un rollo registrado y la resina de entrada registrada, cuando el operador solicita el cierre, entonces el sistema genera el reporte con: rollos, peso bruto/neto/canuto por rollo, total de kilos producidos, kilos de merma y balance de resina.
    - Dado que el reporte está generado, entonces puede visualizarse en pantalla en formato legible para el supervisor sin papel adicional.
  - Fuente: ESTRUSOR.md

---

## Operador de impresión

- **[US-05]** Como operador de impresión, quiero registrar los kilos de tinta (por color) y solvente que recibo de bodega y lo que devuelvo al final del turno, para que el balance de materiales se calcule solo y no me acusen de mala rendición.
  - Criterios de aceptación:
    - Dado que el operador registra kilos de tinta entregada por bodega al inicio del turno, cuando al final registra los kilos devueltos, entonces el sistema calcula el consumo neto por color.
    - Dado que hay una diferencia no explicada entre entrada y salida de un color, entonces el sistema la destaca en el reporte para que el operador la justifique.
  - Fuente: IMPRESOR.md

- **[US-06]** Como operador de impresión, quiero generar el reporte de cierre de turno desde el sistema, para no tener que calcular balances de tintas y solventes a mano mientras limpio los tinteros.
  - Criterios de aceptación:
    - Dado que hay al menos un registro de tinta y al menos un rollo procesado, cuando el operador solicita el cierre, entonces el sistema genera el reporte con: tintas por color (entregadas, devueltas, consumidas), solvente consumido y rollos procesados.
    - Dado que el reporte está generado, entonces puede consultarse y entregarse al supervisor sin papel adicional.
  - Fuente: IMPRESOR.md

---

## Operador de sellado

- **[US-07]** Como operador de sellado, quiero registrar manualmente las bolsas buenas y defectuosas de cada lote, para que el sistema lleve el total del turno sin que yo tenga que confiar en el contador digital de la máquina.
  - Criterios de aceptación:
    - Dado que el operador ingresa el conteo de bolsas buenas y defectuosas de un lote, cuando confirma, entonces el sistema acumula ambos totales para el turno.
    - Dado que el acumulado de bolsas buenas alcanza el tamaño de un paquete (50 o 100 según la orden), entonces el sistema indica que el paquete está completo.
  - Fuente: SELLADOR.md

- **[US-08]** Como operador de sellado, quiero generar el reporte de cierre de turno desde el sistema con el balance de kilaje, para no tener que cuadrar kilos de rollo menos bolsas menos merma con la calculadora al final del turno.
  - Criterios de aceptación:
    - Dado que el turno tiene rollos de entrada registrados, bolsas contadas y merma pesada, cuando el operador solicita el cierre, entonces el sistema calcula: kilos de rollo entrado − kilos de bolsas buenas − kilos de merma y muestra el balance.
    - Dado que el balance tiene una diferencia distinta de cero, entonces el sistema la muestra destacada y solicita una justificación antes de permitir cerrar el turno.
  - Fuente: SELLADOR.md
