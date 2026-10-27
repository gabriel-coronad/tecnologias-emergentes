---
layout: pagina
title: "Proyecto final"
permalink: /proyecto-final/
menu_activo: proyecto
---

**Visualización espacial de redes inalámbricas con realidad mixta** · Meta Quest 3 · Unity

## Descripción

Aplicación de realidad mixta que muestra una representación virtual de una red inalámbrica superpuesta sobre el espacio físico. El usuario ve su entorno real a través del visor y, sobre él, el router, los dispositivos conectados, sus conexiones y parámetros de conectividad ubicados en el espacio.

La aplicación no «ve» las ondas Wi-Fi: obtiene datos de la red cuando es técnicamente posible y los convierte en una representación visual.

## Problema

Las redes inalámbricas y sus parámetros (intensidad de señal, latencia, pérdida de paquetes, tráfico, cobertura, interferencia, atenuación) no son visibles. Normalmente se consultan como números o gráficas, lo que dificulta relacionarlos con el espacio físico donde ocurre la comunicación.

## Objetivo general

Diseñar y desarrollar un prototipo de realidad mixta que permita visualizar de manera espacial e interactiva información relacionada con el funcionamiento y comportamiento de una red inalámbrica dentro de un entorno físico.

## Propósito

- **Práctico:** visualizar y analizar aspectos de una red inalámbrica dentro de un espacio físico.
- **Educativo:** facilitar la comprensión de conceptos de redes y telecomunicaciones mediante una representación tridimensional e interactiva.

## Qué busca representar

- Router y dispositivos conectados.
- Conexiones y flujo de comunicación.
- Latencia e intensidad de señal (RSSI).
- Cobertura, a partir de mediciones tomadas en distintas posiciones.
- Efectos de la distancia y los obstáculos.

## Tipos de información

La aplicación distingue en todo momento el origen de cada dato:

| Tipo | Qué es | Ejemplos |
|---|---|---|
| Real | Medido directamente de la red o del sistema | Latencia medida, RSSI medido, estado de conexión |
| Calculada | Obtenida al procesar datos reales | Promedios, clasificación de cobertura, mapas |
| Simulada | Escenarios hipotéticos con fin educativo | Efecto de materiales, ubicación alternativa del router |

Una simulación nunca se presenta como una medición real.

## Plataforma y herramientas

- Visor: Meta Quest 3 (passthrough y comprensión espacial).
- Motor: Unity.

<!-- Cuando haya avances, agregar aquí una sección "## Desarrollo" con lo construido, capturas y decisiones técnicas. -->
