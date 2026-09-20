# 📦 Optimización de Última Milla y Análisis SLA (Simulación E-commerce)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1MiN2-2MZ-S6l-B8OVLVSZoG09AmYdMch)

## 🎯 Contexto del Negocio
Una empresa de e-commerce enfrenta un estancamiento en su indicador global de entregas a tiempo (OTD). Este proyecto simula, diagnostica y propone soluciones a los cuellos de botella operativos a través de un análisis integral del ciclo de vida del envío, desde la preparación en el almacén hasta la entrega en la última milla.

## 🛠️ Arquitectura y Tecnologías
* **Generación de Datos y EDA:** Python (Pandas, NumPy, Datetime) en Google Colab.
* **Almacenamiento y Diagnóstico:** SQLite3 para la exploración de datos relacionales mediante consultas SQL.
* **Visualización:** Power BI para el desarrollo de un panel gerencial interactivo.

## 📂 Estructura del Repositorio
* `dim_geografia.csv`: Tabla de dimensiones con las 5 ciudades principales de operación y distancias.
* `dim_transportistas.csv`[cite: 19]: Tabla de dimensiones con los 4 proveedores logísticos y sus SLA prometidos.
* `fact_envios.csv`[cite: 19]: Tabla de hechos con 8,500 registros simulados de ciclo de vida de paquetería.
* `logistica_ecommerce.db`: Base de datos SQLite generada para el análisis.
* Proyecto en Colab (`.ipynb`): Script documentado con la generación del modelo estrella y consultas SQL.

## 📊 Hallazgos Clave
Tras analizar el *Cycle Time* aislando las etapas logísticas, se identificaron dos fallas críticas:
1. **Falla Interna (Bodega):** Durante los días viernes y sábado, el tiempo promedio de empaque se dispara a **3.8 días** (frente a 1.3 días en el resto de la semana), evidenciando un colapso en la capacidad operativa de fin de semana.
2. **Falla Externa (Última Milla):** El OTD global (87.83%) está siendo arrastrado por debajo de la meta del 90% debido a dos rutas específicas:
   * **Envía:** Desviación de **+3.0 días** sobre su SLA en envíos hacia Bucaramanga.
   * **Servientrega:** Retraso de **+2.2 días** sobre su SLA en envíos hacia Barranquilla.

## 💡 Recomendaciones Estratégicas
* **Refuerzo Operativo:** Contratar personal de empaque *part-time* exclusivamente para los turnos de viernes y sábado, absorbiendo el pico de demanda y estabilizando los tiempos internos.
* **Enrutamiento Dinámico:** Restringir temporalmente la asignación de paquetes hacia Bucaramanga y Barranquilla a los proveedores Envía y Servientrega, derivando ese volumen a TCC y Coordinadora hasta establecer un plan de mejora continua.

---
**Autor:** William Suárez | Analista de Datos
