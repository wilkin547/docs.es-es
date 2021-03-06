---
title: Leer valores de un convertidor analógico digital
description: Obtenga información sobre cómo leer valores de voltaje variables mediante un convertidor de analógico a digital.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 509616e3423fbb83b74bfbb8ecec1a7df49f0a20
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259750"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="read-values-from-an-analog-to-digital-converter"></a>Leer valores de un convertidor analógico digital

Un convertidor analógico a digital (ADC) es un dispositivo que puede leer un valor de voltaje de entrada analógico y convertirlo en un valor digital. Los ADCs se usan para leer valores de Thermistors, potenciómetros y otros dispositivos que cambian la resistencia en función de ciertas condiciones.

En este tema, usará .NET para leer valores de un ADC a medida que se modula el voltaje de entrada con un potenciómetro.

## <a name="prerequisites"></a>Requisitos previos

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- Convertidor de analógico a digital [MCP3008](https://www.microchip.com/wwwproducts/MCP3008)
- Potenciómetro de tres pines
- Placa de pruebas
- Cables de puente
- Placa de salida de Raspberry PI GPIO (opcional/recomendado)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [prepare-pi-spi](../includes/prepare-pi-spi.md)]

## <a name="prepare-the-hardware"></a>Preparar el hardware

Use los componentes de hardware para compilar el circuito tal y como se muestra en el diagrama siguiente:

:::image type="content" source="../media/rpi-trimpot_spi-thumb.png" alt-text="Un diagrama de Fritz que muestra un circuito con un ADC MCP3008 y un potenciómetro" lightbox="../media/rpi-trimpot_spi.png":::

MCP3008 usa la interfaz de periféricos serie (SPI) para comunicarse. A continuación se indican las conexiones de MCP3008 a Raspberry PI y potenciómetro:

- V<sub>DD</sub> a 3.3 v (se muestra en rojo)
- V<sub>ref</sub> a 3,3 v (rojo)
- AGND a fondo (negro)
- CLK a SCLK (naranja)
- D<sub>out</sub> (naranja)
- D<sub>in</sub> Mosi (naranja)
- CS/SHDN a CE0 (verde)
- DGND a fondo (negro)
- CH0 a eje variable (medio) en potenciómetro (amarillo)

Escriba 3,3 V y el suelo en las clavijas exteriores del potenciómetro. El orden no es importante.

Consulte los siguientes diagramas de pines según sea necesario:

| MCP3008  | Raspberry PI GPIO |
|----------|-------------------|
| :::image type="content" source="../media/mcp3008-diagram-thumb.png" alt-text="Diagrama que muestra el pines del MCP3008" lightbox="../media/mcp3008-diagram.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Diagrama que muestra el pines del encabezado GPIO de Raspberry PI. Image de Raspberry PI Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br />[Image de Raspberry PI Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Creación de la aplicación

Complete los pasos siguientes en el entorno de desarrollo que prefiera:

1. Cree una nueva aplicación de consola .NET mediante la [CLI de .net](../../core/tools/dotnet-new.md) o [Visual Studio](../../core/tutorials/with-visual-studio.md). Asígnele el nombre *AdcTutorial*.

    ```dotnetcli
    dotnet new console -o AdcTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Reemplace el contenido de *Program.cs* por el código siguiente:

    :::code language="csharp" source="~/iot-samples/tutorials/AdcTutorial/Program.cs" :::

    En el código anterior:

    - `hardwareSpiSettings` se establece en una nueva instancia de `SpiConnectionSettings` . El constructor establece el `busId` parámetro en 0 y el `chipSelectLine` parámetro en 0.
    - Una [declaración Using](../../csharp/whats-new/csharp-8.md#using-declarations) crea una instancia de llamando a `SpiDevice` `SpiDevice.Create` y pasando `hardwareSpiSettings` . Esto `SpiDevice` representa el bus SPI. La `using` declaración garantiza que el objeto se desecha y que los recursos de hardware se liberan correctamente.
    - Otra `using` declaración crea una instancia de `Mcp3008` y pasa `SpiDevice` en el constructor.
    - Un `while` bucle se ejecuta indefinidamente. Cada iteración:
        1. Lee el valor de CH0 en el ADC llamando a `mcp.Read(0)` .
        1. Divide el valor por 10,24. MCP3008 es un ADC de 10 bits, lo que significa que devuelve 1024 valores posibles que abarcan 0-1023. La división del valor por 10,24 representa el valor como un porcentaje.
        1. Redondea el valor al entero más próximo.
        1. Escribe el valor en la consola con el formato de porcentaje.
        1. Suspende 500 ms.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Ejecute la aplicación en Raspberry PI cambiando al directorio de implementación y ejecutando el archivo ejecutable.

    ```bash
    ./AdcTutorial
    ```

    Observe el resultado a medida que gira el marcado de potenciómetro. Esto se debe a que el potenciómetro varía la tensión proporcionada a CH0 en el ADC. ADC compara el voltaje de entrada en CH0 con el voltaje de referencia proporcionado a V<sub>ref</sub> para generar un valor.

1. Para finalizar el programa, presione <kbd>Ctrl + C</kbd>.

¡Enhorabuena! Ha usado SPI para leer valores de un convertidor de analógico a digital.

## <a name="get-the-source-code"></a>Obtención del código fuente

El origen de este tutorial está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial).

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Aprenda a usar De uso general entrada/salida para hacer parpadear un LED](../tutorials/blink-led.md)
