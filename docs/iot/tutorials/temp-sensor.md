---
title: Leer condiciones ambientales de un sensor
description: Aprenda a leer termperature, presión barométrica y humedad con las bibliotecas de IoT de .NET.
author: camsoper
ms.author: casoper
ms.date: 11/14/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: bc5c2b9f0876603c152da859547c58b83826969c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259842"
---
# <a name="read-environmental-conditions-from-a-sensor"></a>Leer condiciones ambientales de un sensor

Uno de los escenarios más comunes para dispositivos IoT es la detección de condiciones del entorno. Existen varios sensores disponibles para supervisar la temperatura, la humedad, la presión barométrica y mucho más.

En este tema, usará .NET para leer las condiciones del entorno de un sensor.

## <a name="prerequisites"></a>Requisitos previos

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) humedad/presión barométrica/salida del sensor de temperatura
- Cables de puente
- Placa (opcional)
- Placa de salida de Raspberry PI GPIO (opcional)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!IMPORTANT]
> Hay muchos fabricantes de sesiones de BME280. La mayoría de los diseños son similares y el fabricante no debe tener ninguna diferencia con la funcionalidad. En este tutorial se intenta tener en cuenta las variaciones. Asegúrese de que el desglose de BME280 incluye una interfaz de circuito Inter-Integrated (I2C).

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a>Preparar el hardware

Use los componentes de hardware para compilar el circuito tal y como se muestra en el diagrama siguiente:

:::image type="content" source="../media/rpi-bmp280_i2c-thumb.png" alt-text="Un diagrama de Fritz que muestra la conexión de Raspberry PI a BME280" lightbox="../media/rpi-bmp280_i2c.png":::

A continuación se indican las conexiones desde Raspberry PI al dispositivo de BME280:

- 3,3 v a VIN *o* 3V3 (se muestra en rojo)
- De fondo a GND (negro)
- SDA (GPIO 2) a SDI *o* SDA (azul)
- SCL (GPIO 3) a SCK *o* SCL (naranja)

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Creación de la aplicación

Complete los pasos siguientes en el entorno de desarrollo que prefiera:

1. Cree una nueva aplicación de consola .NET mediante la [CLI de .net](../../core/tools/dotnet-new.md) o [Visual Studio](../../core/tutorials/with-visual-studio.md). Asígnele el nombre *SensorTutorial*.

    ```dotnetcli
    dotnet new console -o SensorTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Reemplace el contenido de *Program.cs* por el código siguiente:

    :::code language="csharp" source="~/iot-samples/tutorials/SensorTutorial/Program.cs" :::

    En el código anterior:

    - `i2cSettings` se establece en una nueva instancia de `I2cConnectionSettings` . El constructor establece el `busId` parámetro en 1 y el `deviceAddress` parámetro en `Bme280.DefaultI2cAddress` .

        > [!IMPORTANT]
        > Algunos fabricantes de BME280 usan el valor de dirección secundaria. Para esos dispositivos, use `Bme280.SecondaryI2cAddress` .

    - Una [declaración Using](../../csharp/whats-new/csharp-8.md#using-declarations) crea una instancia de llamando a `I2cDevice` `I2cDevice.Create` y pasando `i2cSettings` . Esto `I2cDevice` representa el bus I2C. La `using` declaración garantiza que el objeto se desecha y que los recursos de hardware se liberan correctamente.
    - Otra `using` declaración crea una instancia de `Bme280` para representar el sensor. `I2cDevice`Se pasa en el constructor.
    - El tiempo necesario para que el chip tome medidas con la configuración actual (predeterminada) del chip se recupera mediante una llamada a `GetMeasurementDuration` .
    - Un `while` bucle se ejecuta indefinidamente. Cada iteración:
        1. Borra la consola.
        1. Establece el modo de energía en `Bmx280PowerMode.Forced` . Esto obliga al chip a realizar una medición, almacenar los resultados y, a continuación, entrar en suspensión.
        1. Lee los valores de temperatura, presión, humedad y altitud.

            > [!NOTE]
            > La altitud se calcula mediante el enlace del dispositivo. Esta sobrecarga de `TryReadAltitude` utiliza la presión de nivel de mar media para generar una estimación.

        1. Escribe las condiciones del entorno actuales en la consola.
        1. Suspende 1000 ms.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Ejecute la aplicación en Raspberry PI cambiando al directorio de implementación y ejecutando el archivo ejecutable.

    ```bash
    ./SensorTutorial
    ```

    Observe la salida del sensor en la consola.

1. Para finalizar el programa, presione <kbd>Ctrl + C</kbd>.

¡Enhorabuena! Ha usado I2C para leer valores de un sensor de presión de temperatura/humedad/barométrica.

## <a name="get-the-source-code"></a>Obtención del código fuente

El origen de este tutorial está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial).

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Obtenga información sobre cómo mostrar texto en una pantalla LCD](../tutorials/lcd-display.md)
