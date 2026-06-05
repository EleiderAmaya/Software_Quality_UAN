# Informe — Taller E2E

## Parte 1 — Instalación y ejecución inicial

Instalación y arranque (resumen):

```bash
base) eleider@Macs-MacBook-Pro e2e_testing % pytest tests/ -v
============ test session starts ============
platform darwin -- Python 3.13.5, pytest-9.0.3, pluggy-1.5.0 -- /opt/miniconda3/bin/python3.13
cachedir: .pytest_cache
rootdir: /Users/eleider/Software_Quality_UAN/talleres/e2e_testing
plugins: mock-3.15.1, base-url-2.1.0, playwright-0.8.0, anyio-4.13.0
collected 5 items

tests/test_tareas_e2e.py::TestPaginaPrincipal::test_pagina_carga PASSED [ 20%]
tests/test_tareas_e2e.py::TestPaginaPrincipal::test_titulo_visible PASSED [ 40%]
tests/test_tareas_e2e.py::TestCrearTarea::test_formulario_presente PASSED [ 60%]
tests/test_tareas_e2e.py::TestCrearTarea::test_agregar_tarea_no_lanza_error PASSED [ 80%]
tests/test_tareas_e2e.py::TestCompletarTarea::test_completar_tarea_no_lanza_error PASSED [100%]

============= 5 passed in 2.90s =============
(base) eleider@Macs-MacBook-Pro e2e_testing %
```

### Observación inicial

Al ejecutar lo anterior las pruebas iniciales pasan correctamente.

### Pregunta

¿Las pruebas realmente están verificando comportamiento útil del sistema?

### Respuesta (tono coloquial, universitario)

No. Que los tests pasen no significa que lpruebe correctamente el flujo pueden haber falso positivos. Las pruebas actuales son mas validaciones rapidas: revisan que la página abra o que algunos elementos como selectores no lancen error, pero no comprueban que la tarea se guarde, si estan en la lista o si quedó realmente paso a un estado como completada. Hay validaciones indebidas ( `count() >= 0`) que basicamente siempre pasan, así que pueden dar falsos positivos: el test suena bien, pero no garantiza el comportamiento real.
