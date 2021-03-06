---
title: Hacer parpadear un LED
description: Obtenga información sobre cómo hacer parpadear un LED con las bibliotecas de IoT de .NET.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 0d5db19faac0293b9982731f26dfd85d6ce07b3a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259037"
---
# <a name="blink-an-led"></a>Hacer parpadear un LED

Los pin de e/s de uso general (GPIO) se pueden controlar individualmente. Esto resulta útil para controlar LED, retransmisiones y otros dispositivos con estado. En este tema, usará .NET y los pin de GPIO de Raspberry PI para potenciar un LED y parpadear repetidamente.

## <a name="prerequisites"></a>Requisitos previos

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- LED de 5 mm
- resistencia de 330 Ω
- Placa de pruebas
- Cables de puente
- Placa de salida de Raspberry PI GPIO (opcional/recomendado)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [ensure-ssh](../includes/ensure-ssh.md)]

## <a name="prepare-the-hardware"></a>Preparar el hardware

Use los componentes de hardware para compilar el circuito tal y como se muestra en el diagrama siguiente:

:::image type="content" source="../media/rpi-led_bb-thumb.png" alt-text="Un diagrama de Fritz que muestra un circuito con un LED y una resistencia" lightbox="../media/rpi-led_bb.png":::

La imagen anterior muestra las siguientes conexiones:

- GPIO 18 a LED ánodo (mayor, plomo positivo)
- Cátodo LED (más corto y negativo) hasta 330 Ω (extremo)
- 330 Ω resistencia (otro extremo) a la base

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Creación de la aplicación

Complete los pasos siguientes en el entorno de desarrollo que prefiera:

1. Cree una nueva aplicación de consola .NET mediante la [CLI de .net](../../core/tools/dotnet-new.md) o [Visual Studio](../../core/tutorials/with-visual-studio.md). Asígnele el nombre *BlinkTutorial*.

    ```dotnetcli
    dotnet new console -o BlinkTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Reemplace el contenido de *Program.cs* por el código siguiente:

    :::code language="csharp" source="~/iot-samples/tutorials/BlinkTutorial/Program.cs" :::

    En el código anterior:

    - Una [declaración Using](../../csharp/whats-new/csharp-8.md#using-declarations) crea una instancia de `GpioController` . La `using` declaración garantiza que el objeto se desecha y que los recursos de hardware se liberan correctamente.
    - El PIN 18 de GPIO está abierto para la salida
    - Un `while` bucle se ejecuta indefinidamente. Cada iteración:
        1. Escribe un valor en el PIN de GPIO 18. Si `ledOn` es true, escribe `PinValue.High` (ON). De lo contrario, escribe `PinValue.Low` .
        1. Suspende 1000 ms.
        1. Alterna el valor de `ledOn` .

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Ejecute la aplicación en Raspberry PI cambiando al directorio de implementación y ejecutando el archivo ejecutable.

    ```bash
    ./BlinkTutorial
    ```

    El LED parpadea y se activa cada segundo.

1. Para finalizar el programa, presione <kbd>Ctrl + C</kbd>.

¡Enhorabuena! Ha usado GPIO para hacer parpadear un LED.

## <a name="get-the-source-code"></a>Obtención del código fuente

El origen de este tutorial está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial).

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Obtenga información sobre cómo leer condiciones ambientales desde un sensor](../tutorials/temp-sensor.md)
