# Opia Python ML 🚀

Proyecto de Machine Learning desarrollado en Python enfocado en el entrenamiento, evaluación y despliegue de modelos predictivos de regresión (utilizando el dataset *California Housing* / scikit-learn) a través de una API REST con FastAPI.

---

## 📌 Tabla de Contenidos

- [Descripción General](#-descripción-general)
- [Arquitectura y Estructura](#-arquitectura-y-estructura)
- [Stack Tecnológico](#-stack-tecnológico)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación y Configuración](#-instalación-y-configuración)
- [Uso y Ejecución](#-uso-y-ejecución)
  - [1. Entrenamiento del Modelo](#1-entrenamiento-del-modelo)
  - [2. Despliegue de la API](#2-despliegue-de-la-api)
- [Endpoints de la API](#-endpoints-de-la-api)
- [Despliegue en la Nube (Render / Cloud)](#-despliegue-en-la-nube-render--cloud)
- [Licencia](#-licencia)

---

## 📖 Descripción General

Este repositorio contiene el pipeline completo de machine learning:
1. **Extracción y Preprocesamiento:** Carga de datos, limpieza, escalado de variables y división entrenamiento/test (`train_test_split`).
2. **Modelado y Evaluación:** Ajuste de algoritmos de regresión (Árboles de Decisión / Random Forest / Regresión Lineal) y evaluación mediante métricas estándar ($R^2$, RMSE, MAE).
3. **Serialización:** Exportación del modelo entrenado y transformadores mediante `joblib`.
4. **Servicio Web (Inferencia):** API creada con **FastAPI** que expone endpoints para realizar predicciones en tiempo real a partir de cargas útiles JSON.

---

## 📂 Arquitectura y Estructura

```text
opia-python-ml/
├── data/                  # Datasets locales o procesados (opcional)
├── models/                # Artefactos del modelo serializado (.joblib / .pkl)
│   └── model.joblib
├── notebooks/             # Exploración y visualización inicial (Jupyter/EDA)
├── src/                   # Código fuente principal
│   ├── __init__.py
│   ├── train.py           # Pipeline de entrenamiento y exportación
│   ├── predict.py         # Lógica de carga del modelo e inferencia
│   └── app.py             # Definición de la API con FastAPI
├── requirements.txt       # Dependencias del proyecto
├── .gitignore
└── README.md