# Non-Parametric Acoustics

Repositorio de código y ejemplos para la estimación robusta de parámetros acústicos en salas mediante métodos no paramétricos (KDE Epanechnikov).

## Estructura del Proyecto

```text
Non_Parametric_Acoustics/
├── requirements.txt              # Lista de dependencias
├── Reverb_Time_Epanechnikov.ipynb  # Notebook con ejemplos paso a paso
├── Room Acoustics Project/       # Carpeta con audios de mediciones reales
│   ├── measurement1.wav
│   ├── measurement2.wav
│   └── ...
└── README.md                     # Documentación del proyecto
```

## Descripción

Este proyecto implementa un **método robusto** para calcular parámetros acústicos (p.ej. TR₆₀, curvas de Schroeder, RASTI) a partir de respuestas al impulso de salas, integrando un **suavizado no paramétrico** basado en **Kernel Density Estimation (Epanechnikov)**. Está pensado para:

* Operar con **equipamiento básico** (globo o fuente impulsiva genérica, micrófono estándar).
* Ser una **alternativa low-cost** a mediciones con dodecaedro o sine-sweep.
* **Reducir la variabilidad** de los resultados en entornos ruidosos.

## Instalación

1. Clona este repositorio:

   ```bash
   git clone https://github.com/SesbastianEP29/Non_Parametric_Acosutics.git
   cd Non_Parametric_Acosutics
   ```

2. Instala las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

## Uso

1. **Ejecuta el notebook** `Reverb_Time_Epanechnikov.ipynb` en Jupyter:

   ```bash
   jupyter notebook Reverb_Time_Epanechnikov.ipynb
   ```

2. En el notebook encontrarás:

   * Lectura y filtrado de audios de `Room Acoustics Project/`.
   * Cálculo de la curva de Schroeder.
   * Suavizado con `kde_epanechnikov` en dB.
   * Extracción de TR₆₀ clásico y robusto.
   * Visualizaciones comparativas (curvas, boxplots, mapas de calor).

3. **Carpeta de datos**: coloca tus propios `.wav` en `Room Acoustics Project/` y ajusta las rutas en el notebook.

## Funciones Clave

* `kde_epanechnikov(x, fs, h_ms)`: suavizado non-paramétrico de la curva de Schroeder en dB.
* Cálculo de TR₆₀ mediante derivada en dB/s y promedio de pendiente.
* Generación de boxplots y mapas interpolados.

## Estructura de Datos

* **Audios**: respuestas al impulso en formato WAV (mono, 16/24 bit, cualquier fs).
* **Notebook**: ejemplos comentados para replicar el flujo completo.
* **requirements.txt**: dependencias principales:

  * numpy
  * scipy
  * matplotlib
  * plotly


