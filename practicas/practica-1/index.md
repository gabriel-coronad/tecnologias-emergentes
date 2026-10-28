---
title: "Práctica 1 · GameObject y parque de diversiones"
clase: "Clase 1 · Fundamentos y estructura de Unity"
orden: 1
portada: capturas/03-parque-decorado.png
---

## Desarrollo

### Figuras geométricas

Creé un proyecto nuevo en Unity llamado *Practica_1_RM* y, dentro de la carpeta *Scene*, creé la escena *objetos*. En ella agregué las figuras geométricas que ofrece Unity (cubo, esfera, cápsula, cilindro, plano y quad), modifiqué su Transform y las acomodé en fila: a todas les cambié la posición y a algunas las giré.

![Escena objetos](capturas/01-objetos.png)
*Escena «objetos» con las seis figuras geométricas.*

### Parque de diversiones

Creé la escena *Parque_diversiones* y usé el paquete gratuito *Low Poly Houses Free Pack* de la Asset Store, que incluye una rueda de la fortuna.

![Rueda de la fortuna y su jerarquía](capturas/02-rueda-jerarquia.png)
*Rueda de la fortuna y su jerarquía.*

Después decoré el parque con pasto, una fuente, bancas, faroles, botes de basura y arbustos, y coloqué todo dentro de un objeto padre llamado *Parque* para ajustar su tamaño.

![Parque decorado](capturas/03-parque-decorado.png)
*Parque de diversiones decorado.*

## Video

## Propuesta de proyecto final

Mi proyecto final se llama *Visualización espacial de redes inalámbricas con realidad mixta*. Es una aplicación para el visor Meta Quest 3 en la que el usuario ve su habitación real a través del visor y, sobre ella, una representación virtual de su red Wi-Fi: el router, los dispositivos conectados (como una computadora o un celular) y las conexiones entre ellos. La aplicación también mostrará datos de la red, como la latencia o la intensidad de la señal.

Además, el usuario podrá recorrer la habitación y medir la señal en distintos lugares. En cada lugar donde mida quedará una marca de color que indica qué tan buena es la señal ahí, y con todas las marcas se formará un mapa de la cobertura de la red.

Así usaría los conceptos de esta práctica:

- **GameObjects:** cada elemento que aparece en la escena: el router, cada dispositivo, las líneas de conexión y cada marca de medición.
- **Jerarquía:** un objeto padre *Red* que contenga al router y a los dispositivos, de modo que al moverlo se acomode toda la red en la habitación. Cada dispositivo tendría como hijo una etiqueta con sus datos, que se movería junto con él.
- **Prefabs:** un prefab de dispositivo, para crear cada dispositivo de la red a partir del mismo original, y un prefab de marca de medición, por ejemplo una esfera, que se crearía cada vez que el usuario mide la señal y cambiaría de color según qué tan fuerte sea.

Es una propuesta inicial que puede cambiar durante el desarrollo.

## Lo que observé y aprendí

Todo objeto en Unity tiene un Transform que define su posición, rotación y tamaño. En una jerarquía, lo que le pasa al objeto padre les pasa también a sus hijos: si se mueve, gira o cambia de tamaño, los hijos lo siguen. Los prefabs son objetos que se pueden reutilizar, y todas sus copias dependen del original.
