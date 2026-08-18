
# 📞 ConnectaTel - Análisis Estadístico y Segmentación de Clientes

## 🎯 Objetivo del Proyecto
El objetivo de este proyecto es analizar el comportamiento de uso de los servicios móviles (llamadas y mensajes) de los clientes de **ConnectaTel** en México y Colombia durante el periodo 2022-2024. A través de la exploración, limpieza y segmentación de datos, se identificaron patrones de consumo, usuarios atípicos (*Power Users*) y oportunidades comerciales para optimizar la oferta de planes.

---

## 📊 Datasets Utilizados
El análisis integra tres fuentes de datos principales:
1. `plans.csv`: Catálogo de planes actuales (precio mensual, minutos, mensajes y GB incluidos, costo por exceso).
2. `users_latam.csv`: Información demográfica y contractual de los clientes (edad, ciudad, fecha de registro, plan, fecha de baja/churn).
3. `usage.csv`: Registro detallado del uso real del servicio (llamadas, duración, mensajes, longitud y fecha).

---

## 🛠️ Herramientas y Librerías
* **Lenguaje:** Python 3.x
* **Entorno:** Jupyter Notebook / JupyterLab
* **Librerías principales:**
  * `pandas` & `numpy`: Manipulación, combinación y limpieza de estructuras de datos.
  * `matplotlib` & `seaborn`: Exploración visual, histogramas, boxplots y gráficos de frecuencias.

---

## 🔄 Etapas del Análisis
1. **Carga y Exploración Inicial:** Inspección de estructuras (`.info()`, `.shape`), tipos de datos e identificación de inconsistencias.
2. **Calidad de Datos y Limpieza:**
   * Tratamiento de valores faltantes (distinción de nulos por diseño MAR vs. falta de dato).
   * Imputación de valores *sentinels* (`-999` en edad con la mediana, `?` en ciudad con `NA`).
   * Corrección de fechas fuera de rango (años futuros como 2026 convertidos a `NaT`).
3. **Métricas Agregadas (Summary Statistics):** Construcción del perfil de uso por usuario (`cant_mensajes`, `cant_llamadas`, `cant_minutos_llamada`).
4. **Visualización y Detección de Outliers:** Evaluación de distribuciones y cálculo de límites IQR. Se decidió conservar los valores atípicos de alto consumo por representar usuarios de gran valor estratégico.
5. **Segmentación de Clientes:**
   * **Por Uso:** Categorización en *Bajo uso*, *Uso medio* y *Alto uso*.
   * **Por Edad:** Clasificación en *Joven* (<30), *Adulto* (30-59) y *Adulto Mayor* (≥60).
6. **Insight Ejecutivo:** Elaboración de conclusiones sobre ARPU, retención de clientes y propuestas para el negocio.

---

## 💡 Principales Hallazgos y Recomendaciones
* **Diseño de Plan Intermedio (*Mid-Tier*):** Crear una oferta que capture a los clientes de "Uso Medio" del plan Básico antes de escalar al plan Premium.
* **Estrategia de Upselling:** Migrar proactivamente a los clientes de "Alto Uso" que superan su cuota en el plan Básico hacia el plan Premium.
* **Empaquetamiento Modular:** Ofrecer aditivos (*add-ons*) específicos de voz o mensajes para usuarios con patrones intensivos en un solo canal.
