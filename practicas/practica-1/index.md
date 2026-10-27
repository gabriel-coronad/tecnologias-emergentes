---
title: "Práctica 1 · GameObject y parque de diversiones"
clase: "Clase 1 · Fundamentos y estructura de Unity"
orden: 1
portada: capturas/03-parque-decorado.png
---

## Qué pide la práctica

> **Game Object.** Crea un nuevo proyecto 3D Core llamado "Practica_1_RM". Crea una carpeta llamada "Scene" y una escena nueva llamada "objetos". Identifica y crea todas las figuras geométricas que observas en "3D object" y modifica su componente Transform.

> **Parque de diversiones.** Crea una nueva escena en la carpeta "Scene" con el nombre Parque_diversiones. Crea un parque de diversiones donde priorices jerarquías, ya que en el siguiente paso tendrá movimiento y crearás una interacción completa.

> **Paso 6.** Proponer ejemplo de proyecto final: GameObject, Jerarquía, Prefab. Documentar lo observado y comprendido.

*Fuente: presentación «Unity» (clase 1), diapositivas 9 a 11.*

## Desarrollo

### Escena «objetos»

Proyecto **3D (Built-In Render Pipeline)** llamado `Practica_1_RM` en Unity 2022.3.58f1, con la carpeta `Scene`. En la escena `objetos` creé las seis figuras de *GameObject → 3D Object* (**Cube, Sphere, Capsule, Cylinder, Plane y Quad**) y les cambié su **Transform** para acomodarlas en fila sobre el plano:

| Figura | Position | Rotation | Scale |
|---|---|---|---|
| Plane | 0, 0, 0 | 0, 0, 0 | 1.5, 1, 1 |
| Cube | -5, 0.5, 0 | 0, 45, 0 | 1.5, 1, 1 |
| Sphere | -2.5, 0.75, 0 | 0, 0, 0 | 1.5, 1.5, 1.5 |
| Capsule | 0, 1, 0 | 0, 0, 30 | 1, 1, 1 |
| Cylinder | 2.5, 1, 0 | 0, 0, 0 | 1, 1, 1 |
| Quad | 5, 1, 0 | 0, 0, 15 | 1.5, 1.5, 1 |

### Escena «Parque_diversiones»

Usé el paquete gratuito **Low Poly Houses Free Pack** de la Asset Store, que incluye una rueda de la fortuna y elementos de decoración.

- **Rueda de la fortuna:** armé su jerarquía pensando en el movimiento de la siguiente práctica. Un objeto vacío `CentroGiro`, colocado en el centro del aro, contiene el aro y las 10 cabinas; al girarlo, girará todo junto.
- **Escala:** metí la rueda y la decoración en un padre `Parque` con escala 0.3, para que todo quedara proporcionado.
- **Decoración:** terreno de pasto, fuente, bancas, faroles, basureros y arbustos, todos **prefabs** del paquete, organizados en grupos dentro de `Decoracion`.

```
Parque                  (escala 0.3)
├── RuedaFortuna
│   └── ferris wheel    (base)
│       └── CentroGiro  (centro de giro)
│           ├── rotation wheel (aro)
│           └── cabin 1 … cabin 10
└── Decoracion
    ├── Camino → land
    └── Parquecito → Fuente, Bancas, Faroles, Basureros, Cercas
```

**Problema encontrado:** al crear el proyecto, Unity mostró `DirectoryNotFoundException` en un archivo de `Library\PackageCache`. La ruta medía 260 caracteres y Unity solo acepta hasta 259. Lo resolví moviendo el proyecto a una ruta corta.

## Capturas

![Escena objetos](capturas/01-objetos.png)
*Escena «objetos»: las seis figuras y el Transform del Cube.*

![Rueda de la fortuna y su jerarquía](capturas/02-rueda-jerarquia.png)
*Rueda de la fortuna con su jerarquía desplegada.*

![Parque decorado](capturas/03-parque-decorado.png)
*Parque decorado y la jerarquía de la decoración.*

## Propuesta de proyecto final

*Propuesta preliminar: puede cambiar durante el desarrollo del proyecto.*

**Visualización espacial de redes inalámbricas con realidad mixta** (Meta Quest 3).

- **GameObjects:** el router, cada dispositivo (laptop, celular, TV) y cada punto donde se mide la señal.
- **Jerarquía:** un objeto `Red` que contiene al `Router`, un grupo `Dispositivos` (cada uno con su línea de conexión y su etiqueta de latencia) y un grupo `Mediciones`. Al reubicar la red en la habitación, basta con mover `Red`.
- **Prefabs:** `Dispositivo` (modelo, línea de conexión y etiqueta), con una instancia por dispositivo, y `PuntoMedicion` (esfera que cambia de color según la intensidad de la señal), con una instancia por lugar medido.

## Lo que observé y aprendí

- **Transform** define dónde está un objeto (Position), cuánto está girado (Rotation) y qué tan grande es (Scale). Todo GameObject lo tiene.
- Para apoyar una figura en el piso, su posición Y debe ser la mitad de su altura.
- El **Quad** solo se ve por un lado: de espaldas a la cámara desaparece.
- En una **jerarquía**, lo que le pasa al padre les pasa a los hijos: si se mueve, rota o escala, los hijos lo siguen. Las posiciones de los hijos son **locales**, medidas desde su padre.
- **Las escalas se multiplican** a lo largo de la jerarquía. Por eso un solo padre con escala 0.3 deja todo el parque proporcionado.
- Un **prefab** es un objeto reutilizable: todas sus copias en la escena salen del mismo original. Para reorganizar los hijos de un prefab hay que desempacarlo (*Unpack*), y entonces pierde el enlace con el original.
