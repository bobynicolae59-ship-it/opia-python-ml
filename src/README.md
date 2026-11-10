# Despliegue de la Aplicación

A continuación se documentan los pasos seguidos para el despliegue del proyecto en la plataforma Render y la sincronización con el repositorio.

Autores: Javier Martín Bosque, Nicolae Poenaru

## 1. Creación de la cuenta
- Se accedió a la plataforma en la nube [Render](https://render.com/).
- Se hizo clic en el botón de registro (**Sign Up**).
- Se seleccionó la opción de registro mediante **GitHub** para vincular ambas cuentas. Esto autoriza a Render a acceder a los repositorios de GitHub sin necesidad de configurar claves SSH adicionales.

## 2. Configuración del repositorio
- Dentro del panel de control de Render, se seleccionó **New** > **Web Service**.
- Se eligió la opción **Build and deploy from a Git repository**.
- Se buscó y seleccionó el repositorio del proyecto: `bobynicolae59-ship-it/opia-python-ml`.
- Se rellenaron los detalles del despliegue:
  - **Name:** `opia-python-ml`
  - **Region:** Frankfurt (EU Central)
  - **Branch:** `main`
  - **Runtime:** `Python 3`
  - **Plan:** `Free`

## 3. Comando de despliegue
Para que la plataforma instale las dependencias y arranque la aplicación FastAPI, se introdujeron los siguientes comandos en la configuración del servicio:
- **Build Command:** `pip install -r requirements.txt`
- **Start Command:** `uvicorn src.app:app --host 0.0.0.0 --port $PORT`

## 4. URL final
Tras terminar el proceso de compilación y despliegue (estado *Live*), la API quedó publicada y accesible en la siguiente dirección web:
- **URL de la aplicación:** https://opia-python-ml-9jhx.onrender.com
- **URL de GitHub:** https://github.com/bobynicolae59-ship-it/opia-python-ml

## 5. Documentación de la API de Predicción (California Housing)

## Descripción general
La API cuenta con un endpoint principal para realizar estimaciones del precio medio de viviendas utilizando el modelo de Machine Learning entrenado.

## Ejemplo de Petición (Request)
```json
{
  "MedInc": 4.7,
  "HouseAge": 25.0,
  "AveRooms": 5.2,
  "AveBedrms": 1.0,
  "Population": 1200.0,
  "AveOccup": 3.0,
  "Latitude": 37.88,
  "Longitude": -122.23
}
```

## Ejemplo de Respuesta (Response)
```json
{
  "med_house_val": 1.76159
}
```
