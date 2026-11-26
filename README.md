<div align="center">

# OPTIMIZACIÓN NUMÉRICA

### Unidad 1 · Práctica: Solución de Ejercicios

**Manufactura de muebles: maximización de ganancias y análisis de la función de producción.**

**Python · NumPy · SymPy · Matplotlib · Google Colab · Jupyter / Binder**

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/edtech-mx-ve/optimizacion.numerica/main?urlpath=lab/tree/Unidad-1_Practica_Optimizacion_Numerica.ipynb)
[![Abrir en Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/edtech-mx-ve/optimizacion.numerica/blob/main/Unidad-1_Practica_Optimizacion_Numerica.ipynb)

[Repositorio GitHub](https://github.com/edtech-mx-ve/optimizacion.numerica) · [Notebook de la práctica](Unidad-1_Practica_Optimizacion_Numerica.ipynb)

</div>

> **Repositorio de destino:** https://github.com/edtech-mx-ve/optimizacion.numerica
>
> **Estado:** repositorio asignado y enlaces de acceso configurados en este README. La publicación de los archivos en `main` y la ejecución en Binder están pendientes de verificación. El notebook se entrega sin salidas de ejecución almacenadas.

## 1. Presentación y alcance

La práctica corresponde a la Unidad 1 del programa de Optimización. Su propósito es determinar la cantidad de muebles que maximiza las ganancias y analizar cómo el capital y el trabajo influyen en la producción, a partir de los ejercicios presentados por el Dr. Luis Julián Domínguez Pérez (2026).

**Institución:** Instituto Internacional de Aguascalientes.  
**Maestría:** Inteligencia Artificial para la Transformación Digital.  
**Programa:** Optimización · Unidad 1.  
**Alumno:** Antonio Nicolás Toro González.  
**Tutor:** Dr. Luis Julián Domínguez Pérez.  
**Fecha:** noviembre de 2026.

Los ejercicios originales se estudian de manera independiente. La solución alternativa del apartado 6.1 toma como referencia los resultados de producción y ganancia óptimas y declara su supuesto de elaboración propia. La prospección del apartado 7 plantea un estudio futuro, sin implementar la prueba ni anticipar sus resultados.

## 2. Formulación matemática

### 2.1. Problema univariado

$$P(q)=40q-0.5q^2$$

$q$ representa la cantidad de muebles; $P(q)$, la ganancia. La búsqueda exhaustiva evalúa los 80 enteros de 0 a 79 y el cálculo diferencial utiliza la formulación continua. El intervalo computacional no constituye una restricción física de capacidad.

### 2.2. Problema multivariado

$$F(K,L)=K^{0.34}L^{0.66}$$

$K$ representa las horas-máquina y $L$ las horas-hombre. Las derivadas parciales se estudian para $K,L>0$; la gráfica de producción incluye el cero. No se establece una restricción presupuestaria ni de disponibilidad.

## 3. Métodos y resultados de referencia

| Método | Procedimiento | Resultado |
|---|---|---|
| 01 · Búsqueda exhaustiva | Evaluación de alternativas finitas. | 40 muebles; ganancia de 800 unidades monetarias. |
| 02 · Primera derivada | Localización del punto estacionario. | $q=40$; $P'(40)=0$. |
| 03 · Segunda derivada | Evaluación de la curvatura. | $P''(q)=-1$; máximo global único en el problema univariado. |
| 04 · Derivadas parciales | Análisis de capital y trabajo. | Producción creciente en el interior positivo; sin máximo finito en el modelo sin restricciones. |
| 6.1 · Solución alternativa | Combinaciones de recursos para alcanzar la producción y ganancia óptimas. | Múltiples combinaciones de $K,L$ con $F=40$ y $P=800$, bajo el supuesto declarado. |

Cada método presenta fundamento matemático, código, resultados, gráfica y conclusión. Las siete figuras del notebook se generan al ejecutar sus celdas; las dos figuras de la solución alternativa están en celdas independientes.

### 3.1. Solución alternativa

Se supone que la función de producción representa la cantidad de muebles: $q=F(K,L)$. Al sustituir en la función de ganancias:

$$P(K,L)=40F(K,L)-0.5[F(K,L)]^2$$

Las combinaciones óptimas satisfacen:

$$K^{0.34}L^{0.66}=40$$

$$L=\left(\frac{40}{K^{0.34}}\right)^{1/0.66},\qquad K>0$$

La ganancia máxima del modelo se alcanza en toda esa isocuanta. Para seleccionar una única combinación conveniente sería necesario conocer costos o disponibilidad de recursos y establecer un criterio de selección.

*Elaboración propia a partir de las funciones presentadas por el Dr. Domínguez Pérez (2026).*

### 3.2. Prospección: análisis de sensibilidad

Se propone explorar cómo varían las ganancias ante cambios en la cantidad producida respecto al óptimo. Se estudiaría el impacto económico, el margen de variación aceptable y su posible utilidad para planificar la producción. Esta propuesta no está ejecutada ni se presentan conclusiones anticipadas.

## 4. Enfoque metodológico

**Planteamiento → formulación matemática → implementación → resultados → visualización → interpretación → reflexión.**

La implementación conserva la lógica de los ejemplos docentes, con ajustes de sintaxis, funciones reutilizables, validación de entradas, manejo de errores y registro de eventos. No se requieren datos externos, GPU, credenciales, APIs ni servicios de pago.

## 5. Arquitectura y estructura de archivos

```text
Optimizacion_Numerica/
├── README.md
├── Unidad-1_Practica_Optimizacion_Numerica.ipynb
└── requirements.txt
```

| Componente | Función |
|---|---|
| Python 3.13 | Versión de referencia; comprobado localmente con 3.13.5. |
| NumPy | Cálculo numérico y búsqueda exhaustiva. |
| SymPy | Cálculo de derivadas y resolución de ecuaciones. |
| Matplotlib | Representación gráfica bidimensional y tridimensional. |
| IPython / matplotlib-inline | Presentación de ecuaciones y figuras en Jupyter. |
| Jupyter / Binder | Ejecución interactiva en el navegador. |

`requirements.txt` fija las versiones de las dependencias directas observadas en la ejecución local. No constituye un bloqueo completo de dependencias transitivas. La versión de Python en Binder dependerá del entorno que construya el servicio.

## 6. Implementación y ejecución

### 6.1. Google Colab

Abrir el [notebook en Google Colab](https://colab.research.google.com/github/edtech-mx-ve/optimizacion.numerica/blob/main/Unidad-1_Practica_Optimizacion_Numerica.ipynb) una vez publicado, o subir el archivo manualmente a [Google Colab](https://colab.research.google.com/), y seleccionar **Entorno de ejecución → Ejecutar todas**. Utilizar CPU. Las bibliotecas científicas normalmente están disponibles en Colab; si faltan, instalarlas en esa sesión.

### 6.2. Windows / JupyterLab

Desde la carpeta del proyecto, en PowerShell y con Python 3.13 instalado:

```powershell
py -3.13 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m pip install jupyterlab
.\.venv\Scripts\python.exe -m pip check
.\.venv\Scripts\python.exe -m jupyterlab
```

**URL local habitual:** http://localhost:8888/lab (utilizar la URL exacta indicada por Jupyter si cambia el puerto o requiere un token). Abrir el notebook y ejecutar todas sus celdas en orden.

### 6.3. Verificación técnica

La copia de prueba del notebook se ejecutó íntegramente en Python 3.13.5 mediante un kernel Jupyter: 9 celdas de código y 7 figuras PNG generadas, sin errores de las celdas. El archivo de distribución conserva 26 celdas totales, 9 de código sin ejecutar y ninguna salida almacenada.

La prueba utilizó un entorno existente, no una instalación nueva de `requirements.txt`. El despliegue en Binder aún no se ha probado. Debe verificarse después de publicar.

## 7. Repositorio GitHub y publicación en Binder

**Repositorio de destino:** https://github.com/edtech-mx-ve/optimizacion.numerica  
**Nombre del repositorio:** `optimizacion.numerica`  
**Rama de publicación:** `main`  
**Visibilidad requerida para MyBinder público:** pública.  
**Archivo principal:** `Unidad-1_Practica_Optimizacion_Numerica.ipynb`

El repositorio se administra desde la carpeta local existente `Optimizacion_Numerica`. No es necesario crear otra carpeta ni clonar nuevamente el proyecto.

### 7.1. Publicación desde PowerShell

Desde la carpeta local, comprobar la configuración de Git:

```powershell
git status
git remote -v
```

Si el repositorio local todavía no se ha inicializado, ejecutar `git init`. Si aún no existe el remoto `origin`, configurarlo con:

```powershell
git remote add origin https://github.com/edtech-mx-ve/optimizacion.numerica.git
```

Con el remoto correcto y el repositorio de destino vacío, publicar únicamente los tres archivos del proyecto:

```powershell
git branch -M main
git add README.md Unidad-1_Practica_Optimizacion_Numerica.ipynb requirements.txt
git diff --cached --name-only
git commit -m "Publicar practica de optimizacion numerica"
git push -u origin main
```

Si el repositorio remoto ya contiene commits, revisar y sincronizar su historial antes de publicar; no forzar la subida. Para actualizaciones posteriores del README, basta con revisar el cambio, agregar `README.md`, confirmar y publicar en `main`.

### 7.2. Ejecución en Binder y Google Colab

- [Ejecutar práctica en Binder](https://mybinder.org/v2/gh/edtech-mx-ve/optimizacion.numerica/main?urlpath=lab/tree/Unidad-1_Practica_Optimizacion_Numerica.ipynb)
- [Abrir práctica en Google Colab](https://colab.research.google.com/github/edtech-mx-ve/optimizacion.numerica/blob/main/Unidad-1_Practica_Optimizacion_Numerica.ipynb)

Los enlaces apuntan a la rama `main` y al notebook oficial. Para utilizarlos, los tres archivos deben estar publicados en la raíz del repositorio público. En Binder, esperar la construcción del entorno y ejecutar las celdas del notebook en orden. En Colab, seleccionar **Entorno de ejecución → Ejecutar todas**.

**Validación pendiente:** comprobar después de publicar que ambos enlaces abren el notebook correcto, que Binder instala las dependencias de `requirements.txt` y que las celdas generan las siete figuras sin errores. Los enlaces definidos no acreditan por sí mismos un despliegue operativo.

**Documentación:** [Guía de Binder](https://mybinder.readthedocs.io/en/latest/introduction.html) · [Configuración de repo2docker](https://repo2docker.readthedocs.io/en/latest/config_files/).

## 8. Limitaciones, seguridad y uso académico

- Las funciones y coeficientes son datos de los ejercicios; no representan necesariamente información de una empresa real.
- El problema multivariado original no establece límites de recursos. La solución alternativa depende del supuesto explícito $q=F(K,L)$.
- No se ha ejecutado la prospección de sensibilidad.
- Binder ofrece sesiones temporales; el archivo debe descargarse si se desea conservar cambios. Su disponibilidad y tiempos de arranque dependen del servicio.
- La publicación pública expondrá los nombres incluidos en la portada; revisar autorización y derechos de publicación antes de subir el proyecto.
- No se incluyen materiales docentes completos, datos privados, secretos, credenciales ni una licencia de redistribución no autorizada.

## 9. Referencias de consulta

Se conservan las cinco referencias bibliográficas del notebook. En particular, la fuente de los ejercicios es:

Domínguez Pérez, L. J. (2026). *Optimización numérica: Introducción* [Diapositivas de presentación]. Instituto Internacional de Aguascalientes.

Documentación de bibliotecas: [NumPy](https://numpy.org/doc/stable/) · [SymPy](https://docs.sympy.org/latest/) · [Matplotlib](https://matplotlib.org/stable/).

---

<div align="center">

**OPTIMIZACIÓN NUMÉRICA · Unidad 1 · Práctica: Solución de Ejercicios**

*Fundamentación matemática, implementación computacional e interpretación de resultados.*

</div>
