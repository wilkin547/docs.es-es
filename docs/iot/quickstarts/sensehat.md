---
title: 'Inicio rápido: uso de .NET para impulsar un sombrero de sentido de Raspberry PI'
description: Comience a trabajar con las bibliotecas de IoT de .NET en 5 minutos con una detección HAT, una placa de complemento para Raspberry PI.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: quickstart
ms.prod: dotnet
ms.openlocfilehash: 2919db55304590f5557aa0cbda50cc4bd6640443
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739535"
---
# <a name="quickstart---use-net-to-drive-a-raspberry-pi-sense-hat"></a>Inicio rápido: uso de .NET para impulsar un sombrero de sentido de Raspberry PI

El [sensor](https://www.raspberrypi.org/products/sense-hat/) de Raspberry PI <span class="docon docon-navigate-external x-hidden-focus"></span> (**H** hardware **a** ttached en **T** OP) es un panel complementario para Raspberry PI. El sombrero de detección está equipado con una matriz de LED RGB de 8 × 8, un joystick de cinco botones e incluye los sensores siguientes:

- Giroscopio
- Acelerómetro
- Magnetómetro
- Temperatura
- Presión barométrica
- Humedad

Esta guía de inicio rápido usa .NET para recuperar los valores del sensor desde el sombrero de detección, responder a la entrada del joystick y controlar la matriz de LED.

## <a name="prerequisites"></a>Requisitos previos

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- Detección HAT

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="run-the-quickstart"></a>Ejecutar la guía de inicio rápido

Adjunte el sombrero de detección a su Raspberry PI. En un símbolo del sistema de bash en Raspberry PI (local o remoto), ejecute el siguiente comando:

```bash
. <(wget -q -O - https://aka.ms/dotnet-iot-sensehat-quickstart)
```

El comando descarga y ejecuta un script. El script:

- Instala el SDK de .NET.
- Clona un repositorio de GitHub que incluye el proyecto de inicio rápido de Sense HAT.
- Compila el proyecto.
- Ejecuta el proyecto.

Observe el resultado de la consola a medida que se muestran los datos del sensor. La matriz LED muestra un píxel amarillo en un campo de color azul. Al mantener el joystick en cualquier dirección, se mueve el píxel amarillo en esa dirección. Al hacer clic en el botón central joystick, el fondo cambia de azul a rojo.

## <a name="get-the-source-code"></a>Obtención del código fuente

El origen de esta guía de inicio rápido está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Aprenda a usar De uso general entrada/salida para hacer parpadear un LED](../tutorials/blink-led.md)
