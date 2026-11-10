# Proyecto de analítica financiera \| IX Concurso ITM 2026

> **Plantilla de trabajo para estudiantes.** Crea una copia de este archivo en el repositorio de tu equipo y reemplaza los textos entre corchetes. Conserva las preguntas como apoyo durante la investigación. No publiques claves de acceso ni información privada.

**Curso:** Lenguajes de Programación · Ingeniería Financiera  
**Concurso:** 12 de noviembre de 2026  
**Simulacro:** 10 de noviembre de 2026  
**Tecnología:** Python \+ Streamlit (datos con yfinance y pandas)

## 1\. Identificación del proyecto

- **Nombre de la aplicación:** FINGENIUS  
- **Equipo e integrantes:** KARINA SILVA DURANGO, SAlLOME MUÑOZ RESTREPO, DANIEL FELIPE GIL BUSTAMANTE  
- **Enlace a la aplicación:** https\://colab.research.google.com/drive/1cMZWe5xl19Az-exGUIu0LiKn50eVC9r\_?usp=sharing  
- &nbsp;  
- &nbsp;  
- **Repositorio del proyecto:** \[URL\]  
- **Última actualización:** 2026-11-05

## 2\. ¿Qué queremos investigar? · S25

**Investiga:** ¿qué significa analizar el comportamiento histórico de un activo financiero? ¿Qué preguntas pueden responderse con datos de mercado y cuáles no?

- **Situación o fenómeno de interés:** El comportamiento histórico de las acciones de Ecopetrol y Argos y Nutresa.&nbsp;  
- **Pregunta principal:** ¿Cómo variaron los precios de las acciones de Ecopetrol, Grupo Argos y Grupo Nutresa en Colombia entre 2021 y 2025?&nbsp;  
- **Objetivo del análisis:** Comparar las variaciones de los tres activos e identificar sus tendencias, aumentos, disminuciones y principales fluctuaciones durante el período estudiado.&nbsp;  
- **Importancia financiera:** Comprender cómo se comportan activos importantes para la economía colombiana y cómo los factores económicos nacionales e internacionales influyen en sus valores.&nbsp;  
- **Preguntas complementarias:**&nbsp;  
- ¿Cuál de los tres activos presentó mayores variaciones?  
- ¿Cuál tuvo el comportamiento más estable?  
- ¿Qué factores económicos influyeron en sus cambios?  
- ¿En qué año se registraron sus mayores aumentos y disminuciones?  
- &nbsp;

> **Comprueba:** ¿tu pregunta identifica activos, variables y un período de estudio? ¿Es posible responderla con datos disponibles?

## 3\. Activos, datos y alcance · S25

**Investiga:** ¿qué activos se ajustan a tu pregunta? ¿qué datos históricos existen? ¿qué frecuencia, período y fuente utilizarás?

| Activo | Símbolo o ticker | Tipo | Razón para incluirlo |
| :---- | :---- | :---- | :---- |
| ECOPETROL | ECOPETROL&nbsp; | Acción | Es una de las empresas más importantes de Colombia. Su precio puede relacionarse con el petróleo y la economía nacional.&nbsp; |
| Grupo Argos&nbsp; | GRUPOARGOS&nbsp; | Acción&nbsp; | Representa sectores como infraestructura y construcción.&nbsp; |
| Grupo Nutresa&nbsp; | NUTRESA | Acción&nbsp; | Representa el sector de alimentos y consumo masivo.&nbsp; |

Fuente de datos: Yahoo Finance, mediante la biblioteca yfinance (https\://ranaroussi.github.io/yfinance/)

- **Período:** \[2021-01-01/2025-01-01\]  
- **Frecuencia:** \[MENSUAL\]  
- **Variables disponibles:** \[Fecha,Precio de cierre ajustado, precio de cierre,Precio máximo, Precio mínimo, Precio de apertura,  volumen\]  
- **Limitaciones de los datos:**&nbsp;  
- Posibles fechas sin registros de negociación por días festivos o suspensión de operaciones.  
- Diferencias en los precios debido a dividendos y ajustes corporativos.  
- Los datos mensuales no permiten observar todas las fluctuaciones diarias.

**Primera prueba:** https\://github.com/kari1020/codigo1/blob/67f6e61bbf6b728390a5014e772b086c0573026c/Verifiaci%C3%B3n\_Activos

## 4\. Metodología de análisis · S25–S26

**Investiga:** ¿qué indicadores permiten responder la pregunta principal? ¿cómo se calculan? ¿qué interpretación y limitaciones tienen?

| Indicador / técnica | ¿Qué mide? | ¿Por qué lo necesitamos? | Implementación |
| :---- | :---- | :---- | :---- |
| Variación porcentual (%)&nbsp; | &nbsp;Cuánto aumentó o disminuyó el valor de un activo entre dos períodos.&nbsp; | Identificar los aumentos y disminuciones de cada activo.&nbsp; | Python (pandas): (precio final \- precio inicial) / precio inicial x 100 |
| Rendimiento mensual (%)&nbsp; | El cambio porcentual del precio respecto al mes anterior.&nbsp; | Identificar los meses con mayores subidas y caídas.&nbsp; | Python (pandas): pct\_change() sobre el precio de cierre ajustado |
| Rendimiento acumulado (%)&nbsp; | El cambio total entre el inicio y el final del período.&nbsp; | Comparar el comportamiento general de los activos entre 2021 y 2025\.&nbsp; | Python (pandas): (último precio / primer precio \- 1\) x 100 sobre el precio de cierre ajustado |
| Volatilidad&nbsp; | Qué tanto varían los rendimientos respecto a su promedio.&nbsp; | Determinar cuál de los activos presentó mayor inestabilidad.&nbsp; | Python (pandas): desviación estándar de los rendimientos mensuales (std) |
| Máximo y mínimo&nbsp; | Los valores más altos y bajos registrados durante el período.&nbsp; | Identificar los puntos extremos del comportamiento histórico.&nbsp; | Python (pandas): max() y min() del precio de cierre ajustado, con su fecha |

No es necesario utilizar todos los indicadores estudiados en clase. Selecciona y justifica únicamente los pertinentes.

### Visualizaciones previstas

| Gráfico | Pregunta que ayuda a responder | Variables | Interpretación esperada |
| :---- | :---- | :---- | :---- |
| Líneas de precio de cierre ajustado (base 100\) | ¿Cómo variaron los precios de los tres activos entre 2021 y 2025? | Fecha y precio de cierre ajustado de los tres activos | Tendencias, aumentos, disminuciones y fluctuaciones de cada activo |
| Barras de volatilidad y rendimiento acumulado | ¿Cuál activo presentó mayores variaciones y cuál fue el más estable? | Rendimiento mensual (%), volatilidad y rendimiento acumulado | Riesgo y rendimiento total de Ecopetrol, Grupo Argos y Grupo Nutresa |

**Primer resultado verificable:** \[Enlace a un cálculo o gráfico realizado con datos reales y una interpretación breve\]

## 5\. Diseño de la aplicación · S25

**Investiga:** ¿cómo se construyen controles, gráficos y métricas con la herramienta elegida? ¿qué sucede cuando el usuario modifica una selección?

- **Usuarios previstos:** Estudiantes, docentes e inversionistas principiantes interesados en el comportamiento histórico de acciones colombianas  
- **Entradas y filtros:** Selección de activos (Ecopetrol, Grupo Argos, Grupo Nutresa), rango de fechas y tipo de precio  
- **Secciones de la interfaz:** Pantalla principal, comparación de precios y rendimientos, riesgo (volatilidad) y conclusiones  
- **Resultados visibles:** Gráficos de precios y rendimientos, tabla de indicadores (variación, rendimiento acumulado, volatilidad, máximo y mínimo) y explicaciones breves  
- **Interacción principal:** Al cambiar los activos o el rango de fechas, la aplicación recalcula los indicadores y actualiza los gráficos y las tablas

**Flujo previsto:**  
Selección de activos y parámetros → Obtención de datos → Preparación y cálculos → Visualización → Interpretación.

**Boceto o esquema:** \[Inserta una imagen o enlace al diseño, por ejemplo `docs/boceto.png`\]

**Decisión técnica:** Python, por pandas y yfinance para descargar y procesar los datos; Streamlit, porque permite crear una interfaz interactiva rápido y publicarla con un enlace

## 6\. Construcción y pruebas · S26 (5 de noviembre)

Actualiza esta sección durante el laboratorio de desarrollo.

- **Componentes implementados:** Todavía no hay código implementado: el equipo está en la fase de diseño (secciones 2 a 5). Los componentes previstos son la descarga de datos, el cálculo de indicadores, los gráficos y los filtros de la aplicación.  
- **Cómo ejecutar la aplicación:** Por definir cuando exista el código de la aplicación.  
- **Dependencias:** Por definir; las bibliotecas previstas son streamlit, yfinance, pandas y plotly.  
- **Pruebas realizadas:** Todavía no se han realizado pruebas de la aplicación; la única verificación hasta ahora es la primera prueba de los activos (sección 3).  
- **Errores conocidos y cómo se resolvieron:** Aún no hay errores registrados porque no hay código. Riesgos previstos: meses sin datos por festivos (se limpian con dropna()) y diferencias entre precio de cierre y precio ajustado (se usa el cierre ajustado).  
- **Pendientes antes del simulacro:** Terminar la aplicación en Streamlit con los filtros y gráficos de la sección 5, probar los indicadores con datos reales, publicar el enlace de la aplicación y ensayar la sustentación de 3 a 5 minutos.

> No afirmes que una función está implementada si aún no ha sido probada.

## 7\. Hallazgos e interpretación · S26–S28

Para cada hallazgo importante, registra:

1. **Evidencia:** \[Gráfico, tabla o indicador con enlace\]  
2. **Qué muestra:** \[Describe el comportamiento observado\]  
3. **Interpretación financiera:** \[Explica su significado en relación con la pregunta\]  
4. **Limitaciones:** \[Qué no puedes concluir de los datos\]

**Conclusión provisional o final:** \[Respuesta sustentada a la pregunta principal\]

> Los resultados históricos no garantizan rendimientos futuros.

## 8\. Simulacro · S27 (10 de noviembre)

**Guion de sustentación (3–5 minutos):**

- Problema financiero y activos.  
- Datos y metodología.  
- Demostración de interactividad.  
- Hallazgos e interpretación.  
- Conclusión y limitaciones.

**Retroalimentación recibida:** \[Observaciones del docente o compañeros\]

| Ajuste necesario | Responsable | Estado |
| :---- | :---- | :---- |
| \[Ajuste\] | \[Integrante\] | \[Pendiente / en proceso / resuelto\] |

## 9\. Presentación final · S28 (12 de noviembre)

- **Enlace funcional de la aplicación:** \[URL\]  
- **Versión final / commit:** \[Enlace\]  
- **Evidencia de presentación:** \[Enlace autorizado\]  
- **Conclusiones finales:** \[Síntesis\]  
- **Limitaciones y posibles mejoras:** \[Descripción\]

## 10\. Bitácora de trabajo y aportes

| Fecha | Integrante(s) | Investigación o decisión | Avance técnico / evidencia | Próximo paso |
| :---- | :---- | :---- | :---- | :---- |
| 2026-11-03 | \[Nombre\] | \[Qué investigamos\] | \[Enlace a código o documento\] | \[Acción\] |
| 2026-11-05 | \[Nombre\] | \[Decisiones\] | \[Evidencia\] | \[Acción\] |
| 2026-11-10 | \[Nombre\] | \[Retroalimentación\] | \[Cambio\] | \[Acción\] |

## Recursos de consulta

- [Libro de programación y analítica financiera del curso](https://github.com/vyolete/proyecto_analitica_financiera)  
- [Documentación de yfinance](https://ranaroussi.github.io/yfinance/)  
- [Documentación de pandas](https://pandas.pydata.org/docs/)  
- [Documentación de Streamlit](https://docs.streamlit.io/)  
- [Documentación de Shiny para R](https://shiny.posit.co/r/)

**Uso del documento:** En S25 desarrolla especialmente las secciones 2 a 5 y registra tu primera prueba; en S26, S27 y S28 actualiza el mismo README. No dupliques información en entregas separadas.