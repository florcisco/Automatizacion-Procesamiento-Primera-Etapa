# Automatización del Procesamiento de Cursadas — Primera Etapa

Herramienta desarrollada en Python para automatizar el procesamiento de información académica a partir de archivos Excel y OpenDocument.

El proyecto busca reemplazar un proceso manual y repetitivo por una herramienta capaz de validar, procesar y organizar automáticamente la información necesaria para generar los reportes académicos.

## Objetivo

El objetivo principal es automatizar la primera etapa del procesamiento de información académica, reduciendo tareas manuales y permitiendo realizar controles de calidad sobre los datos antes de continuar con las etapas posteriores.

Entre las tareas realizadas se encuentran:

* Procesamiento de archivos `.xlsx` y `.ods`.
* Validación de archivos y contenido.
* Procesamiento de información de alumnos.
* Conversión de ausencias según las condiciones establecidas.
* Cálculo de promedios.
* Generación de reportes.
* Identificación de alumnos en condición de libres.
* Control de inconsistencias en los datos.
* Detección de posibles errores en nombres y apellidos.
* Preparación de la información necesaria para la segunda etapa del proceso.
* Generación de la hoja `REG 2ET`.

## Problema

El proceso original requería realizar manualmente diferentes tareas sobre varias planillas académicas.

Esto implicaba revisar información, modificar datos, realizar cálculos, generar hojas de trabajo y controlar posibles inconsistencias.

Además de consumir tiempo, la realización manual de estas tareas aumentaba la posibilidad de cometer errores durante el procesamiento.

## Solución

Se desarrolló una aplicación en Python que centraliza estas tareas y automatiza el procesamiento de los archivos.

La herramienta realiza validaciones, procesa la información, ejecuta los cálculos correspondientes y genera los reportes necesarios para continuar con el proceso académico.

De esta manera, se busca estandarizar el procedimiento, reducir tareas repetitivas y mejorar el control sobre la calidad de los datos.

## Flujo general del proyecto

```text
┌─────────────────────────────────────┐
│         PRIMERA ETAPA               │
│                                     │
│ Procesamiento y preparación         │
│ de la información académica         │
└─────────────────┬───────────────────┘
                  │
                  ▼
┌─────────────────────────────────────┐
│          SEGUNDA ETAPA              │
│                                     │
│ Cálculo y procesamiento             │
│ de recuperatorios                   │
└─────────────────┬───────────────────┘
                  │
                  ▼
┌─────────────────────────────────────┐
│          PRÓXIMAS ETAPAS            │
│                                     │
│ Promociones y condiciones           │
│ finales                             │
└─────────────────────────────────────┘
```

## Tecnologías utilizadas

* Python
* Tkinter
* OpenPyXL
* Pandas
* Threading
* Queue

## Características principales

### Procesamiento de archivos

La aplicación permite trabajar con archivos académicos en formatos:

* `.xlsx`
* `.xlsm`
* `.ods`

### Validación de información

Antes de realizar el procesamiento se ejecutan diferentes controles sobre los archivos y sus contenidos.

Entre ellos:

* Validación de archivos.
* Control de datos obligatorios.
* Validación de notas.
* Control de alumnos.
* Verificación de información académica.
* Detección de inconsistencias.

### Procesamiento de ausencias

La herramienta procesa la información correspondiente a las inasistencias y aplica las condiciones establecidas para el cálculo de los promedios.

Las ausencias son contempladas durante el procesamiento para obtener resultados consistentes.

### Cálculo de promedios

El programa automatiza el cálculo de los promedios correspondientes a los alumnos a partir de la información disponible en los archivos de entrada.

Esto evita tener que realizar manualmente los cálculos sobre las planillas.

### Generación de reportes

Como resultado del procesamiento se generan diferentes hojas con información organizada para continuar con las tareas académicas.

Entre ellas se encuentran:

* `REPORTE`
* `LIB`
* `REG`
* `INAS`
* `REG 2ET`

### Control de calidad de datos

Uno de los objetivos principales del proyecto es detectar posibles inconsistencias en los datos antes de finalizar el procesamiento.

Entre los controles implementados se encuentra la detección de posibles problemas relacionados con los nombres y apellidos de los alumnos.

Por ejemplo, se pueden identificar situaciones como apellidos repetidos o información que requiere una revisión manual.

Estos controles permiten utilizar la herramienta no solamente para automatizar cálculos, sino también como mecanismo de control de calidad de la información.

## Interfaz gráfica

La aplicación cuenta con una interfaz gráfica desarrollada con `Tkinter`.

Durante el procesamiento se muestra una ventana de progreso con las diferentes etapas de ejecución.

El flujo de procesamiento contempla:

1. Elegir archivos.
2. Validar archivos.
3. Validar contenido.
4. Procesar información.
5. Realizar cálculos.
6. Generar reportes.

El uso de `threading` y `queue` permite mantener la interfaz disponible mientras se ejecutan las tareas de procesamiento.

## Capturas

### Selección de archivos

![Selección de archivos](capturas/elegir_archivo.png)

### Archivo original

![Archivo original](capturas/archivo_original.png)

### Ventana de finalización

![Ventana de finalización](capturas/ventana_finalizacion.png)

### Archivo procesado

![Archivo procesado](capturas/archivo_procesado.png)

### Control de apellidos

![Control de apellidos](capturas/alerta_apellidos.png)

## Instalación

Clonar el repositorio:

```bash
git clone https://github.com/florcisco/Automatizacion-Procesamiento-Primera-Etapa.git
```

Ingresar al directorio:

```bash
cd Automatizacion-Procesamiento-Primera-Etapa
```

Instalar las dependencias:

```bash
pip install -r requirements.txt
```

## Ejecución

Ejecutar el programa principal:

```bash
python Procesamiento-Primera-Etapa.py
```

También puede utilizarse una versión ejecutable generada mediante PyInstaller, evitando la necesidad de ejecutar directamente el código fuente.

## Segunda etapa

Esta herramienta corresponde a la **Primera Etapa** de un proceso de automatización académica desarrollado de forma modular.

La información procesada y preparada durante esta etapa sirve como entrada para una segunda herramienta encargada del cálculo y procesamiento de recuperatorios.

### Segunda Etapa — Cálculo de Recuperatorios

La segunda etapa incorpora nuevas validaciones, comparación de información entre diferentes archivos y cálculo de los recuperatorios correspondientes.

[Ver repositorio de la Segunda Etapa](https://github.com/florcisco/Automatizacion-Segunda-Etapa)

## Evolución del proyecto

El proyecto está pensado para continuar creciendo mediante diferentes etapas independientes.

Actualmente se encuentran desarrolladas:

* **Primera etapa:** procesamiento y preparación de la información académica.
* **Segunda etapa:** cálculo y procesamiento de recuperatorios.

Como futuras etapas se contempla continuar automatizando procesos relacionados con:

* Promociones.
* Condiciones finales.
* Otras tareas académicas que actualmente requieren procesamiento manual.

La separación en diferentes herramientas permite que cada etapa pueda desarrollarse, probarse y mantenerse de manera independiente, facilitando posteriormente su integración dentro de un flujo completo de automatización.

## Mejoras implementadas

A lo largo del desarrollo se fueron incorporando diferentes mejoras orientadas a:

* Automatizar tareas que anteriormente se realizaban manualmente.
* Incorporar validaciones de datos.
* Mejorar el control de errores.
* Detectar inconsistencias en la información.
* Reducir tiempos de procesamiento.
* Estandarizar la generación de reportes.
* Facilitar el uso mediante una interfaz gráfica.
* Preparar la información para las etapas posteriores.

## Posibles mejoras futuras

Algunas funcionalidades que podrían incorporarse en futuras versiones:

* Integración de las diferentes etapas en una única aplicación.
* Ampliación de las validaciones de calidad de datos.
* Incorporación de nuevos controles.
* Mejoras en la interfaz gráfica.
* Generación de registros de ejecución.
* Automatización de nuevas etapas del proceso académico.

## Autor

**Francisco Lombroni**

Proyecto desarrollado como parte de un proceso de aprendizaje y desarrollo de herramientas orientadas a la automatización, procesamiento y control de calidad de datos mediante Python.
