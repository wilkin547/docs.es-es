---
title: Mostrar texto en una pantalla LCD
description: Obtenga información sobre cómo mostrar caracteres en una pantalla de cristal líquido con las bibliotecas de IoT de .NET.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: d4c3e373207e23877903491871f4d09e11000c1a
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594733"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="display-text-on-an-lcd"></a>Mostrar texto en una pantalla LCD

Las pantallas de caracteres LCD son útiles para mostrar información sin necesidad de un monitor externo. Las pantallas de caracteres LCD comunes se pueden conectar directamente a los pin de GPIO, pero este enfoque requiere el uso de hasta 10 clavijas de GPIO. En el caso de los escenarios que requieren la conexión a una combinación de dispositivos, la desvotación de forma que gran parte del encabezado GPIO a una presentación de caracteres no suele ser práctica.

Muchos fabricantes venden el carácter LCD 20x4 con un expansor de GPIO integrado. La visualización de caracteres se conecta directamente al expansor de GPIO, que luego se conecta a Raspberry PI a través del protocolo serie de Inter-Integrated circuito (I2C).

En este tema, usará .NET para mostrar texto en una pantalla de caracteres LCD mediante un expansor de I2C GPIO.

## <a name="prerequisites"></a>Requisitos previos

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [presentación de caracteres LCD 20x4 con la interfaz I2C](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c)<span class="docon docon-navigate-external x-hidden-focus"></span>
- Cables de puente
- Placa (opcional/recomendado)
- Placa de salida de Raspberry PI GPIO (opcional/recomendado)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!NOTE]
> Hay muchos fabricantes de pantallas de caracteres LCD. La mayoría de los diseños son idénticos y el fabricante no debe tener ninguna diferencia con la funcionalidad. Como referencia, este tutorial se desarrolló con el [LCD2004 del descubierto](https://www.sunfounder.com/lcd2004-module.html) <span class="docon docon-navigate-external x-hidden-focus"></span> .

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a>Preparar el hardware

Use cables de puente para conectar los cuatro PIN del expansor de I2C GPIO al Raspberry PI como se indica a continuación:

- GND a suelo
- VCC a 5 v
- SDA a SDA (GPIO 2)
- SCL a SCL (GPIO 3)

Consulte las siguientes figuras según sea necesario:

| Interfaz I2C (parte posterior de la pantalla) | Raspberry PI GPIO |
|---------------------------------|-------------------|
| :::image type="content" source="../media/character-display-i2c-thumb.png" alt-text="Imagen de la parte posterior de la presentación de caracteres que muestra el expansor de I2C GPIO." lightbox="../media/character-display-i2c.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Diagrama que muestra el pines del encabezado GPIO de Raspberry PI. Image de Raspberry PI Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br />[Image de Raspberry PI Foundation](https://www.raspberrypi.org/documentation/usage/gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span> .
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Creación de la aplicación

Complete los pasos siguientes en el entorno de desarrollo que prefiera:

1. Cree una nueva aplicación de consola .NET mediante la [CLI de .net](../../core/tools/dotnet-new.md) o [Visual Studio](../../core/tutorials/with-visual-studio.md). Asígnele el nombre *LcdTutorial*.

    ```dotnetcli
    dotnet new console -o LcdTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Reemplace el contenido de *Program.cs* por el código siguiente:

    :::code language="csharp" source="~/iot-samples/tutorials/LcdTutorial/Program.cs" :::

    En el código anterior:

    - Una [declaración Using](../../csharp/whats-new/csharp-8.md#using-declarations) crea una instancia de llamando a `I2cDevice` `I2cDevice.Create` y pasando un nuevo `I2cConnectionSettings` con los `busId` parámetros y `deviceAddress` . Esto `I2cDevice` representa el bus I2C. La `using` declaración garantiza que el objeto se desecha y que los recursos de hardware se liberan correctamente.

        > [!WARNING]
        > La dirección del dispositivo para el expansor de GPIO depende del chip usado por el fabricante. Los ampliadores de GPIO equipados con un PCF8574 usan la dirección, mientras que las que usan los `0x27` chips de PCF8574A usan `0x3F` . Consulte la documentación de su LCD.

    - Otra `using` declaración crea una instancia de `Pcf8574` y pasa `I2cDevice` en el constructor. Esta instancia representa el expansor del GPIO.
    - Otra `using` declaración crea una instancia de `Lcd2004` para representar la presentación. Se pasan varios parámetros al constructor que describen la configuración que se va a usar para comunicarse con el expansor de GPIO. El expansor de GPIO se pasa como `controller` parámetro.
    - Un `while` bucle se ejecuta indefinidamente. Cada iteración:
        1. Borra la pantalla.
        1. Establece la posición del cursor en la primera posición de la línea actual.
        1. Escribe la hora actual en la presentación en la posición actual del cursor.
        1. Procesa una iteración en el contador de línea actual.
        1. Suspende 1000 ms.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Ejecute la aplicación en Raspberry PI cambiando al directorio de implementación y ejecutando el archivo ejecutable.

    ```bash
    ./LcdTutorial
    ```

    Observe la pantalla del carácter LCD a medida que se muestra la hora actual en cada línea.

    > [!TIP]
    > Si la pantalla está encendida, pero no ve ningún texto, intente ajustar el contraste en la parte posterior de la pantalla.

1. Para finalizar el programa, presione <kbd>Ctrl + C</kbd>.

¡Enhorabuena! Ha mostrado texto en un LCD con un expansor y un expansor de GPIO.

## <a name="get-the-source-code"></a>Obtención del código fuente

El origen de este tutorial está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Aprenda a usar De uso general entrada/salida para hacer parpadear un LED](../tutorials/blink-led.md)
