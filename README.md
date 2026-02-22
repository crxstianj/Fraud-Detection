# Sistema de Detección de Fraude con Tarjetas de Crédito

## Descripción

Sistema de detección automática de fraude financiero en tarjetas de credito usando Machine Learning y detección de anomalías.  
El proyecto implementa un pipeline completo desde preparación de datos hasta despliegue del modelo como API REST.

El sistema identifica transacciones fraudulentas en datasets altamente desbalanceados mediante reducción de dimensionalidad y modelos de detección de outliers.

---

## Objetivo

- Detectar transacciones fraudulentas automáticamente.
- Reducir falsos positivos en clientes legítimos.
- Construir un sistema escalable para producción.
- Desplegar el modelo como servicio de predicción.

---

## Dataset

**Credit Card Fraud Detection Dataset**

- 284,807 transacciones
- 492 fraudes (0.172%)
- Variables anonimizadas mediante PCA (V1–V28)
- Sin valores nulos ni duplicados

Variables principales:

- `Time` → tiempo de transacción  
- `Amount` → monto  
- `V1–V28` → componentes principales  
- `Class` → etiqueta objetivo  

---

## Flujo del Sistema

```
Transacción → Transformación LDA → Detección de anomalía → Predicción
```

### Preparación de datos
- Análisis exploratorio de datos.
- Selección de características.
- Reducción de dimensionalidad con LDA.
- Validación de calidad de datos.

### Modelado
- Isolation Forest.
- Elliptic Envelope (modelo final).
- Local Outlier Factor.

### Evaluación
- Precision
- Recall
- F1 Score
- ROC-AUC

---

## Resultados

**Modelo final: Elliptic Envelope**

- Precision fraude: 0.80
- Recall fraude: 0.80
- F1-score: 0.80
- Latencia < 1 ms por predicción

---

## Tecnologías

- Python
- Scikit-learn
- Pandas / NumPy
- FastAPI
- Docker

---

## Despliegue

- API REST para predicciones en tiempo real.
- Modelo serializado y contenedorizado.
- Documentación automática con Swagger UI.
- Sistema portable y escalable.

---
