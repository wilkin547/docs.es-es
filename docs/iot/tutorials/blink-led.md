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
# <a name="blink-an-led"></a><span data-ttu-id="44bca-103">Hacer parpadear un LED</span><span class="sxs-lookup"><span data-stu-id="44bca-103">Blink an LED</span></span>

<span data-ttu-id="44bca-104">Los pin de e/s de uso general (GPIO) se pueden controlar individualmente.</span><span class="sxs-lookup"><span data-stu-id="44bca-104">General-purpose I/O (GPIO) pins can be controlled individually.</span></span> <span data-ttu-id="44bca-105">Esto resulta útil para controlar LED, retransmisiones y otros dispositivos con estado.</span><span class="sxs-lookup"><span data-stu-id="44bca-105">This is useful for controlling LEDs, relays, and other stateful devices.</span></span> <span data-ttu-id="44bca-106">En este tema, usará .NET y los pin de GPIO de Raspberry PI para potenciar un LED y parpadear repetidamente.</span><span class="sxs-lookup"><span data-stu-id="44bca-106">In this topic, you will use .NET and your Raspberry Pi's GPIO pins to power an LED and blink it repeatedly.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44bca-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="44bca-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="44bca-108">LED de 5 mm</span><span class="sxs-lookup"><span data-stu-id="44bca-108">5 mm LED</span></span>
- <span data-ttu-id="44bca-109">resistencia de 330 Ω</span><span class="sxs-lookup"><span data-stu-id="44bca-109">330 Ω resistor</span></span>
- <span data-ttu-id="44bca-110">Placa de pruebas</span><span class="sxs-lookup"><span data-stu-id="44bca-110">Breadboard</span></span>
- <span data-ttu-id="44bca-111">Cables de puente</span><span class="sxs-lookup"><span data-stu-id="44bca-111">Jumper wires</span></span>
- <span data-ttu-id="44bca-112">Placa de salida de Raspberry PI GPIO (opcional/recomendado)</span><span class="sxs-lookup"><span data-stu-id="44bca-112">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [ensure-ssh](../includes/ensure-ssh.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="44bca-113">Preparar el hardware</span><span class="sxs-lookup"><span data-stu-id="44bca-113">Prepare the hardware</span></span>

<span data-ttu-id="44bca-114">Use los componentes de hardware para compilar el circuito tal y como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="44bca-114">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-led_bb-thumb.png" alt-text="Un diagrama de Fritz que muestra un circuito con un LED y una resistencia" lightbox="../media/rpi-led_bb.png":::

<span data-ttu-id="44bca-116">La imagen anterior muestra las siguientes conexiones:</span><span class="sxs-lookup"><span data-stu-id="44bca-116">The image above depicts the following connections:</span></span>

- <span data-ttu-id="44bca-117">GPIO 18 a LED ánodo (mayor, plomo positivo)</span><span class="sxs-lookup"><span data-stu-id="44bca-117">GPIO 18 to LED anode (longer, positive lead)</span></span>
- <span data-ttu-id="44bca-118">Cátodo LED (más corto y negativo) hasta 330 Ω (extremo)</span><span class="sxs-lookup"><span data-stu-id="44bca-118">LED cathode (shorter, negative lead) to 330 Ω resistor (either end)</span></span>
- <span data-ttu-id="44bca-119">330 Ω resistencia (otro extremo) a la base</span><span class="sxs-lookup"><span data-stu-id="44bca-119">330 Ω resistor (other end) to ground</span></span>

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="44bca-120">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="44bca-120">Create the app</span></span>

<span data-ttu-id="44bca-121">Complete los pasos siguientes en el entorno de desarrollo que prefiera:</span><span class="sxs-lookup"><span data-stu-id="44bca-121">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="44bca-122">Cree una nueva aplicación de consola .NET mediante la [CLI de .net](../../core/tools/dotnet-new.md) o [Visual Studio](../../core/tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="44bca-122">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="44bca-123">Asígnele el nombre *BlinkTutorial*.</span><span class="sxs-lookup"><span data-stu-id="44bca-123">Name it *BlinkTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o BlinkTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="44bca-124">Reemplace el contenido de *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="44bca-124">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/BlinkTutorial/Program.cs" :::

    <span data-ttu-id="44bca-125">En el código anterior:</span><span class="sxs-lookup"><span data-stu-id="44bca-125">In the preceding code:</span></span>

    - <span data-ttu-id="44bca-126">Una [declaración Using](../../csharp/whats-new/csharp-8.md#using-declarations) crea una instancia de `GpioController` .</span><span class="sxs-lookup"><span data-stu-id="44bca-126">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `GpioController`.</span></span> <span data-ttu-id="44bca-127">La `using` declaración garantiza que el objeto se desecha y que los recursos de hardware se liberan correctamente.</span><span class="sxs-lookup"><span data-stu-id="44bca-127">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="44bca-128">El PIN 18 de GPIO está abierto para la salida</span><span class="sxs-lookup"><span data-stu-id="44bca-128">GPIO pin 18 is opened for output</span></span>
    - <span data-ttu-id="44bca-129">Un `while` bucle se ejecuta indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="44bca-129">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="44bca-130">Cada iteración:</span><span class="sxs-lookup"><span data-stu-id="44bca-130">Each iteration:</span></span>
        1. <span data-ttu-id="44bca-131">Escribe un valor en el PIN de GPIO 18.</span><span class="sxs-lookup"><span data-stu-id="44bca-131">Writes a value to GPIO pin 18.</span></span> <span data-ttu-id="44bca-132">Si `ledOn` es true, escribe `PinValue.High` (ON).</span><span class="sxs-lookup"><span data-stu-id="44bca-132">If `ledOn` is true, it writes `PinValue.High` (on).</span></span> <span data-ttu-id="44bca-133">De lo contrario, escribe `PinValue.Low` .</span><span class="sxs-lookup"><span data-stu-id="44bca-133">Otherwise, it writes `PinValue.Low`.</span></span>
        1. <span data-ttu-id="44bca-134">Suspende 1000 ms.</span><span class="sxs-lookup"><span data-stu-id="44bca-134">Sleeps 1000 ms.</span></span>
        1. <span data-ttu-id="44bca-135">Alterna el valor de `ledOn` .</span><span class="sxs-lookup"><span data-stu-id="44bca-135">Toggles the value of `ledOn`.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="44bca-136">Ejecute la aplicación en Raspberry PI cambiando al directorio de implementación y ejecutando el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="44bca-136">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./BlinkTutorial
    ```

    <span data-ttu-id="44bca-137">El LED parpadea y se activa cada segundo.</span><span class="sxs-lookup"><span data-stu-id="44bca-137">The LED blinks off and on every second.</span></span>

1. <span data-ttu-id="44bca-138">Para finalizar el programa, presione <kbd>Ctrl + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="44bca-138">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="44bca-139">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="44bca-139">Congratulations!</span></span> <span data-ttu-id="44bca-140">Ha usado GPIO para hacer parpadear un LED.</span><span class="sxs-lookup"><span data-stu-id="44bca-140">You've used GPIO to blink an LED.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="44bca-141">Obtención del código fuente</span><span class="sxs-lookup"><span data-stu-id="44bca-141">Get the source code</span></span>

<span data-ttu-id="44bca-142">El origen de este tutorial está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial).</span><span class="sxs-lookup"><span data-stu-id="44bca-142">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial).</span></span>

## <a name="next-steps"></a><span data-ttu-id="44bca-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="44bca-143">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="44bca-144">Obtenga información sobre cómo leer condiciones ambientales desde un sensor</span><span class="sxs-lookup"><span data-stu-id="44bca-144">Learn how to read environmental conditions from a sensor</span></span>](../tutorials/temp-sensor.md)
