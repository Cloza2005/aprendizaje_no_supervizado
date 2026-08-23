# Segmentación de clientes RetailMax
## Reporte de recomendaciones para el equipo de Marketing

**Elaborado por:** Claudio Loza
**Área:** Analítica de datos
**Metodología:** Clustering K-Means (aprendizaje no supervisado)
**Base analizada:** 200 clientes registrados

---

## 1. Resumen ejecutivo

Se aplicó un modelo de segmentación no supervisada sobre la base de clientes de RetailMax con el objetivo de identificar grupos con comportamientos de compra homogéneos y, a partir de ellos, orientar la inversión de marketing. El análisis utilizó tres variables: edad, ingreso anual y calificación de gasto (*spending score*). El número óptimo de segmentos se determinó mediante el método del codo, que señaló **cinco clusters** como el punto donde agregar más grupos deja de aportar poder explicativo.

El hallazgo central del ejercicio es que **el poder adquisitivo no predice el gasto**. Los segmentos 2 y 3 registran exactamente el mismo ingreso anual promedio —86.10 mil dólares— pero calificaciones de gasto de 81.53 y 19.36 respectivamente. Ambos grupos concentran juntos el 56% del ingreso total de la cartera, pero solo uno de ellos lo está convirtiendo en ventas. Esta brecha constituye la principal oportunidad comercial detectada y debería concentrar el esfuerzo del próximo ciclo de campañas.

---

## 2. Descripción de los segmentos

| Cluster | Nombre propuesto | Clientes | % base | Edad prom. | Ingreso prom. | Score prom. |
|---|---|---|---|---|---|---|
| 2 | Premium activos | 40 | 20.0% | 32.9 | 86.10k$ | 81.53 |
| 3 | Potencial no capturado | 39 | 19.5% | 39.9 | 86.10k$ | 19.36 |
| 1 | Jóvenes de alta propensión | 54 | 27.0% | 25.2 | 41.09k$ | 62.24 |
| 4 | Maduros estables | 47 | 23.5% | 55.6 | 54.38k$ | 48.85 |
| 0 | Bajo compromiso | 20 | 10.0% | 46.3 | 26.75k$ | 18.35 |

---

## 3. Recomendaciones por segmento

### Prioridad 1 — Cluster 3: "Potencial no capturado" (39 clientes, 19.5%)

Es el segmento más rentable en potencia y el peor atendido hoy. Tiene el ingreso más alto de la cartera junto con el cluster 2, pero apenas gasta. Su edad promedio es siete años mayor que la de los Premium activos.

**Acciones recomendadas:**
1. **Investigación cualitativa previa a invertir.** Antes de lanzar promociones, aplicar entrevistas o encuestas a una muestra de este grupo. El bajo gasto con alto ingreso indica una barrera —surtido inadecuado, mala experiencia previa, preferencia por la competencia— que un descuento no resuelve.
2. **Evitar la promoción por precio.** El descuento es ineficaz en clientes cuya restricción no es económica, y erosiona margen sin necesidad.
3. **Probar propuesta de valor diferenciada:** categorías premium, atención personalizada, servicios de conveniencia (entrega programada, asesoría, personal shopper).

**Meta sugerida:** elevar el score promedio de 19 a 35 en doce meses. Dado que el segmento representa 27.7% del ingreso agregado de la cartera, incluso una conversión parcial supera el retorno de cualquier otra acción.

### Prioridad 2 — Cluster 2: "Premium activos" (40 clientes, 20.0%)

Alto ingreso y alto gasto. Es el segmento de mayor valor actual y el de mayor riesgo si se descuida.

**Acciones recomendadas:** programa de lealtad de nivel superior con beneficios exclusivos; acceso anticipado a lanzamientos y preventas; *upselling* y venta cruzada hacia categorías de mayor margen; comunicación de baja frecuencia pero alto valor. **La prioridad aquí es retención, no captación.** La pérdida de un cliente de este grupo equivale a la de cuatro del cluster 0.

### Prioridad 3 — Cluster 1: "Jóvenes de alta propensión" (54 clientes, 27.0%)

El segmento más numeroso. Ingreso medio-bajo (41.09k$) pero score de 62.24: gastan por encima de lo que su ingreso sugeriría. Alta propensión a comprar y trayectoria de ingreso creciente por delante.

**Acciones recomendadas:** promociones frecuentes y de ticket accesible; facilidades de pago (meses sin intereses); comunicación por canales digitales y redes sociales; **construcción de marca a largo plazo**, ya que al crecer su ingreso migrarán naturalmente hacia el perfil Premium. Es una inversión a futuro, no solo a resultado inmediato.

### Prioridad 4 — Cluster 4: "Maduros estables" (47 clientes, 23.5%)

Perfil intermedio en las tres variables y el de mayor edad (55.6 años). Constituye el núcleo estable del negocio.

**Acciones recomendadas:** programa de lealtad tradicional por acumulación de puntos; campañas estacionales; comunicación por canales convencionales (correo electrónico, punto de venta) más que digitales. Objetivo: mantener frecuencia, no forzar crecimiento.

### Prioridad 5 — Cluster 0: "Bajo compromiso" (20 clientes, 10.0%)

Ingreso y gasto bajos. Aporta 4.4% del ingreso agregado de la cartera.

**Acciones recomendadas:** mínimo esfuerzo dedicado. Incluir únicamente en campañas masivas de bajo costo marginal. **No se recomienda asignar presupuesto específico**, ya que el costo de adquisición difícilmente se recupera.

---

## 4. Consideraciones metodológicas

Se evaluó incorporar el **sexo** como variable de agrupamiento. El resultado no fue satisfactorio: al añadirla, el algoritmo generó dos clusters divididos casi exclusivamente por género —uno 100% mujeres y otro 0%— con perfiles de edad e ingreso prácticamente idénticos entre sí. Al ser una variable binaria estandarizada, adquiere un peso desproporcionado y consume un cluster en dividir un grupo que era homogéneo en comportamiento de compra.

**Recomendación:** conservar el modelo de tres variables para la segmentación, y utilizar el sexo como variable descriptiva dentro de cada segmento —para ajustar el tono creativo y la selección de medios— pero no como criterio de agrupamiento. Cabe señalar que ningún segmento del modelo final presenta un sesgo de género relevante: la proporción de mujeres oscila entre 48.7% y 60.0%, cercana al balance de la base total.

---

## 5. Limitaciones

Tres advertencias deben acompañar la lectura de estos resultados:

1. **Tamaño de muestra.** Doscientos clientes es una base reducida; el cluster 0 contiene solo veinte casos, por lo que sus promedios son sensibles a valores atípicos.
2. **Origen del *spending score*.** El modelo asume la calificación como un indicador válido de comportamiento de compra. Conviene documentar cómo se construye antes de tomar decisiones presupuestales sobre ella.
3. **Ausencia de variables transaccionales.** No se dispone de frecuencia de compra, ticket promedio, categorías adquiridas ni antigüedad del cliente. Incorporar un modelo **RFM** (Recencia, Frecuencia, Monto) enriquecería sustancialmente la segmentación.

---

## 6. Siguientes pasos propuestos

1. Validar los cinco segmentos con el equipo comercial y confirmar que corresponden a perfiles reconocibles en operación.
2. Ejecutar la investigación cualitativa sobre el cluster 3 antes de comprometer presupuesto.
3. Diseñar una campaña piloto por segmento con medición de resultados a noventa días.
4. Reevaluar el modelo semestralmente: la segmentación no es estática y los clientes migran entre grupos.
5. Ampliar la base de variables con información transaccional para una segunda iteración del modelo.

---

*Reporte generado a partir del análisis contenido en `2_clustering.ipynb`. Modelo K-Means, k=5, `random_state=42`, inercia final 168.25.*
