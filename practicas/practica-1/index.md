---
title: "Práctica 1 · GameObject y parque de diversiones"
clase: "Clase 1 · Fundamentos y estructura de Unity"
orden: 1
portada: capturas/03-parque-decorado.png
---

## Desarrollo

### Figuras geométricas

Creé un proyecto nuevo en Unity llamado *Practica_1_RM* y, dentro de la carpeta *Scene*, la escena *objetos*. En ella agregué las figuras geométricas que ofrece Unity (cubo, esfera, cápsula, cilindro, plano y quad) y modifiqué su Transform para acomodarlas en fila: a todas les cambié la posición, a algunas las giré, como al cubo y a la cápsula, y a otras les cambié el tamaño, como a la esfera y al quad.

### Parque de diversiones

Para el parque creé la escena *Parque_diversiones* y usé un paquete gratuito de la Asset Store, *Low Poly Houses Free Pack*, que incluye una rueda de la fortuna y objetos para decorar.

La rueda la organicé pensando en que en la siguiente práctica tendrá movimiento. Agrupé el aro y las diez cabinas dentro de un objeto vacío colocado en el centro de la rueda; así, al girar ese objeto, girará todo junto mientras la base se queda fija.

Después decoré el parque con pasto, una fuente, bancas, faroles, botes de basura y arbustos, y los agrupé por tipo para mantener la escena ordenada. Para que todo quedara del mismo tamaño que la rueda, coloqué todos los elementos dentro de un objeto padre llamado *Parque* y lo reduje: al cambiar la escala del padre, todo lo que contiene se ajustó al mismo tiempo.

## Capturas

![Escena objetos](capturas/01-objetos.png)
*Escena «objetos» con las seis figuras geométricas.*

![Rueda de la fortuna y su jerarquía](capturas/02-rueda-jerarquia.png)
*Rueda de la fortuna y su jerarquía.*

![Parque decorado](capturas/03-parque-decorado.png)
*Parque de diversiones decorado.*

## Video

## Propuesta de proyecto final

Mi proyecto final es una aplicación de realidad mixta para Meta Quest 3 que muestra una red inalámbrica sobre el espacio real: el router, los dispositivos conectados y la intensidad de la señal en distintos puntos de una habitación. Así se podrían aplicar los conceptos de esta práctica:

- **GameObjects:** el router, cada dispositivo (laptop, celular, televisión) y cada punto donde se mide la señal.
- **Jerarquía:** un objeto *Red* que contenga al router, a los dispositivos y a las mediciones. Cada dispositivo tendría como hijos su línea de conexión y una etiqueta con su latencia. Así, para acomodar la red en la habitación bastaría con mover el objeto *Red*.
- **Prefabs:** uno para los dispositivos y otro para los puntos de medición, por ejemplo una esfera que cambia de color según la intensidad de la señal. Cada dispositivo o medición sería una copia del prefab, y al modificar el original cambiarían todas.

Es una propuesta inicial que puede cambiar durante el desarrollo del proyecto.

## Lo que observé y aprendí

Todo objeto en Unity tiene un Transform, que define su posición, su rotación y su tamaño. Para que una figura quede apoyada sobre el piso, su posición en Y debe ser la mitad de su altura, y algunas figuras, como el quad, solo se ven por un lado.

Lo que más me sirvió fue entender las jerarquías: lo que le pasa a un objeto padre les pasa también a sus hijos. Si el padre se mueve, gira o cambia de tamaño, los hijos lo siguen; por eso pude ajustar todo el parque cambiando solo un objeto, y por eso la rueda podrá girar completa desde su centro.

También entendí la utilidad de los prefabs: son objetos que se pueden reutilizar muchas veces, y todas las copias dependen del original. Las bancas, faroles y arbustos del parque son copias de un mismo prefab.
