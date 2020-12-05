---
title: Leer valores de un convertidor analógico digital
description: Obtenga información sobre cómo leer valores de voltaje variables mediante un convertidor de analógico a digital.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 7cf25f181997ed66639842727be57e7824ef5466
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739992"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="read-values-from-an-analog-to-digital-converter"></a><span data-ttu-id="75dd9-103">Leer valores de un convertidor analógico digital</span><span class="sxs-lookup"><span data-stu-id="75dd9-103">Read values from an analog-to-digital converter</span></span>

<span data-ttu-id="75dd9-104">Un convertidor analógico a digital (ADC) es un dispositivo que puede leer un valor de voltaje de entrada analógico y convertirlo en un valor digital.</span><span class="sxs-lookup"><span data-stu-id="75dd9-104">An analog-to-digital converter (ADC) is a device that can read an analog input voltage value and convert it into a digital value.</span></span> <span data-ttu-id="75dd9-105">Los ADCs se usan para leer valores de Thermistors, potenciómetros y otros dispositivos que cambian la resistencia en función de ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="75dd9-105">ADCs are used for reading values from thermistors, potentiometers, and other devices that change resistance based on certain conditions.</span></span>

<span data-ttu-id="75dd9-106">En este tema, usará .NET para leer valores de un ADC a medida que se modula el voltaje de entrada con un potenciómetro.</span><span class="sxs-lookup"><span data-stu-id="75dd9-106">In this topic, you will use .NET to read values from an ADC as you modulate the input voltage with a potentiometer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75dd9-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="75dd9-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="75dd9-108">[MCP3008](https://www.microchip.com/wwwproducts/MCP3008) <span class="docon docon-navigate-external x-hidden-focus"></span> convertidor de analógico a digital</span><span class="sxs-lookup"><span data-stu-id="75dd9-108">[MCP3008](https://www.microchip.com/wwwproducts/MCP3008) <span class="docon docon-navigate-external x-hidden-focus"></span> analog-to-digital converter</span></span>
- <span data-ttu-id="75dd9-109">Potenciómetro de tres pines</span><span class="sxs-lookup"><span data-stu-id="75dd9-109">Three-pin potentiometer</span></span>
- <span data-ttu-id="75dd9-110">Placa de pruebas</span><span class="sxs-lookup"><span data-stu-id="75dd9-110">Breadboard</span></span>
- <span data-ttu-id="75dd9-111">Cables de puente</span><span class="sxs-lookup"><span data-stu-id="75dd9-111">Jumper wires</span></span>
- <span data-ttu-id="75dd9-112">Placa de salida de Raspberry PI GPIO (opcional/recomendado)</span><span class="sxs-lookup"><span data-stu-id="75dd9-112">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [prepare-pi-spi](../includes/prepare-pi-spi.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="75dd9-113">Preparar el hardware</span><span class="sxs-lookup"><span data-stu-id="75dd9-113">Prepare the hardware</span></span>

<span data-ttu-id="75dd9-114">Use los componentes de hardware para compilar el circuito tal y como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="75dd9-114">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-trimpot_spi-thumb.png" alt-text="Un diagrama de Fritz que muestra un circuito con un ADC MCP3008 y un potenciómetro" lightbox="../media/rpi-trimpot_spi.png":::

<span data-ttu-id="75dd9-116">MCP3008 usa la interfaz de periféricos serie (SPI) para comunicarse.</span><span class="sxs-lookup"><span data-stu-id="75dd9-116">The MCP3008 uses Serial Peripheral Interface (SPI) to communicate.</span></span> <span data-ttu-id="75dd9-117">A continuación se indican las conexiones de MCP3008 a Raspberry PI y potenciómetro:</span><span class="sxs-lookup"><span data-stu-id="75dd9-117">The following are the connections from the MCP3008 to the Raspberry Pi and potentiometer:</span></span>

- <span data-ttu-id="75dd9-118">V<sub>DD</sub> a 3.3 v (se muestra en rojo)</span><span class="sxs-lookup"><span data-stu-id="75dd9-118">V<sub>DD</sub> to 3.3V (shown in red)</span></span>
- <span data-ttu-id="75dd9-119">V<sub>ref</sub> a 3,3 v (rojo)</span><span class="sxs-lookup"><span data-stu-id="75dd9-119">V<sub>REF</sub> to 3.3V (red)</span></span>
- <span data-ttu-id="75dd9-120">AGND a fondo (negro)</span><span class="sxs-lookup"><span data-stu-id="75dd9-120">AGND to ground (black)</span></span>
- <span data-ttu-id="75dd9-121">CLK a SCLK (naranja)</span><span class="sxs-lookup"><span data-stu-id="75dd9-121">CLK to SCLK (orange)</span></span>
- <span data-ttu-id="75dd9-122">D<sub>out</sub> (naranja)</span><span class="sxs-lookup"><span data-stu-id="75dd9-122">D<sub>OUT</sub> to MISO (orange)</span></span>
- <span data-ttu-id="75dd9-123">D<sub>in</sub> Mosi (naranja)</span><span class="sxs-lookup"><span data-stu-id="75dd9-123">D<sub>IN</sub> to MOSI (orange)</span></span>
- <span data-ttu-id="75dd9-124">CS/SHDN a CE0 (verde)</span><span class="sxs-lookup"><span data-stu-id="75dd9-124">CS/SHDN to CE0 (green)</span></span>
- <span data-ttu-id="75dd9-125">DGND a fondo (negro)</span><span class="sxs-lookup"><span data-stu-id="75dd9-125">DGND to ground (black)</span></span>
- <span data-ttu-id="75dd9-126">CH0 a eje variable (medio) en potenciómetro (amarillo)</span><span class="sxs-lookup"><span data-stu-id="75dd9-126">CH0 to variable (middle) pin on potentiometer (yellow)</span></span>

<span data-ttu-id="75dd9-127">Escriba 3,3 V y el suelo en las clavijas exteriores del potenciómetro.</span><span class="sxs-lookup"><span data-stu-id="75dd9-127">Supply 3.3V and ground to the outer pins on the potentiometer.</span></span> <span data-ttu-id="75dd9-128">El orden no es importante.</span><span class="sxs-lookup"><span data-stu-id="75dd9-128">Order is unimportant.</span></span>

<span data-ttu-id="75dd9-129">Consulte los siguientes diagramas de pines según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="75dd9-129">Refer to the following pinout diagrams as needed:</span></span>

| <span data-ttu-id="75dd9-130">MCP3008</span><span class="sxs-lookup"><span data-stu-id="75dd9-130">MCP3008</span></span>  | <span data-ttu-id="75dd9-131">Raspberry PI GPIO</span><span class="sxs-lookup"><span data-stu-id="75dd9-131">Raspberry Pi GPIO</span></span> |
|----------|-------------------|
| :::image type="content" source="../media/mcp3008-diagram-thumb.png" alt-text="Diagrama que muestra el pines del MCP3008" lightbox="../media/mcp3008-diagram.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Diagrama que muestra el pines del encabezado GPIO de Raspberry PI. Image de Raspberry PI Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br /><span data-ttu-id="75dd9-134">[Image de Raspberry PI Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span><span class="sxs-lookup"><span data-stu-id="75dd9-134">[Image courtesy Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span></span>
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="75dd9-135">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="75dd9-135">Create the app</span></span>

<span data-ttu-id="75dd9-136">Complete los pasos siguientes en el entorno de desarrollo que prefiera:</span><span class="sxs-lookup"><span data-stu-id="75dd9-136">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="75dd9-137">Cree una nueva aplicación de consola .NET mediante la [CLI de .net](../../core/tools/dotnet-new.md) o [Visual Studio](../../core/tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="75dd9-137">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="75dd9-138">Asígnele el nombre *AdcTutorial*.</span><span class="sxs-lookup"><span data-stu-id="75dd9-138">Name it *AdcTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o AdcTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="75dd9-139">Reemplace el contenido de *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="75dd9-139">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/AdcTutorial/Program.cs" :::

    <span data-ttu-id="75dd9-140">En el código anterior:</span><span class="sxs-lookup"><span data-stu-id="75dd9-140">In the preceding code:</span></span>

    - <span data-ttu-id="75dd9-141">`hardwareSpiSettings` se establece en una nueva instancia de `SpiConnectionSettings` .</span><span class="sxs-lookup"><span data-stu-id="75dd9-141">`hardwareSpiSettings` is set to a new instance of `SpiConnectionSettings`.</span></span> <span data-ttu-id="75dd9-142">El constructor establece el `busId` parámetro en 0 y el `chipSelectLine` parámetro en 0.</span><span class="sxs-lookup"><span data-stu-id="75dd9-142">The constructor sets the `busId` parameter to 0 and the `chipSelectLine` parameter to 0.</span></span>
    - <span data-ttu-id="75dd9-143">Una [declaración Using](../../csharp/whats-new/csharp-8.md#using-declarations) crea una instancia de llamando a `SpiDevice` `SpiDevice.Create` y pasando `hardwareSpiSettings` .</span><span class="sxs-lookup"><span data-stu-id="75dd9-143">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `SpiDevice` by calling `SpiDevice.Create` and passing in `hardwareSpiSettings`.</span></span> <span data-ttu-id="75dd9-144">Esto `SpiDevice` representa el bus SPI.</span><span class="sxs-lookup"><span data-stu-id="75dd9-144">This `SpiDevice` represents the SPI bus.</span></span> <span data-ttu-id="75dd9-145">La `using` declaración garantiza que el objeto se desecha y que los recursos de hardware se liberan correctamente.</span><span class="sxs-lookup"><span data-stu-id="75dd9-145">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="75dd9-146">Otra `using` declaración crea una instancia de `Mcp3008` y pasa `SpiDevice` en el constructor.</span><span class="sxs-lookup"><span data-stu-id="75dd9-146">Another `using` declaration creates an instance of `Mcp3008` and passes the `SpiDevice` into the constructor.</span></span>
    - <span data-ttu-id="75dd9-147">Un `while` bucle se ejecuta indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="75dd9-147">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="75dd9-148">Cada iteración:</span><span class="sxs-lookup"><span data-stu-id="75dd9-148">Each iteration:</span></span>
        1. <span data-ttu-id="75dd9-149">Lee el valor de CH0 en el ADC llamando a `mcp.Read(0)` .</span><span class="sxs-lookup"><span data-stu-id="75dd9-149">Reads the value of CH0 on the ADC by calling `mcp.Read(0)`.</span></span>
        1. <span data-ttu-id="75dd9-150">Divide el valor por 10,24.</span><span class="sxs-lookup"><span data-stu-id="75dd9-150">Divides the value by 10.24.</span></span> <span data-ttu-id="75dd9-151">MCP3008 es un ADC de 10 bits, lo que significa que devuelve 1024 valores posibles que abarcan 0-1023.</span><span class="sxs-lookup"><span data-stu-id="75dd9-151">The MCP3008 is a 10-bit ADC, which means it returns 1024 possible values ranging 0-1023.</span></span> <span data-ttu-id="75dd9-152">La división del valor por 10,24 representa el valor como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="75dd9-152">Dividing the value by 10.24 represents the value as a percentage.</span></span>
        1. <span data-ttu-id="75dd9-153">Redondea el valor al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="75dd9-153">Rounds the value to the nearest integer.</span></span>
        1. <span data-ttu-id="75dd9-154">Escribe el valor en la consola con el formato de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="75dd9-154">Writes the value to the console formatted as a percentage.</span></span>
        1. <span data-ttu-id="75dd9-155">Suspende 500 ms.</span><span class="sxs-lookup"><span data-stu-id="75dd9-155">Sleeps 500 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="75dd9-156">Ejecute la aplicación en Raspberry PI cambiando al directorio de implementación y ejecutando el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="75dd9-156">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./AdcTutorial
    ```

    <span data-ttu-id="75dd9-157">Observe el resultado a medida que gira el marcado de potenciómetro.</span><span class="sxs-lookup"><span data-stu-id="75dd9-157">Observe the output as you rotate the potentiometer dial.</span></span> <span data-ttu-id="75dd9-158">Esto se debe a que el potenciómetro varía la tensión proporcionada a CH0 en el ADC.</span><span class="sxs-lookup"><span data-stu-id="75dd9-158">This is due to the potentiometer varying the voltage supplied to CH0 on the ADC.</span></span> <span data-ttu-id="75dd9-159">ADC compara el voltaje de entrada en CH0 con el voltaje de referencia proporcionado a V<sub>ref</sub> para generar un valor.</span><span class="sxs-lookup"><span data-stu-id="75dd9-159">The ADC compares the input voltage on CH0 to the reference voltage supplied to V<sub>REF</sub> to generate a value.</span></span>

1. <span data-ttu-id="75dd9-160">Para finalizar el programa, presione <kbd>Ctrl + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="75dd9-160">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="75dd9-161">Felicidades.</span><span class="sxs-lookup"><span data-stu-id="75dd9-161">Congratulations!</span></span> <span data-ttu-id="75dd9-162">Ha usado SPI para leer valores de un convertidor de analógico a digital.</span><span class="sxs-lookup"><span data-stu-id="75dd9-162">You've used SPI to read values from an analog-to-digital converter.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="75dd9-163">Obtención del código fuente</span><span class="sxs-lookup"><span data-stu-id="75dd9-163">Get the source code</span></span>

<span data-ttu-id="75dd9-164">El origen de este tutorial está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="75dd9-164">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="75dd9-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="75dd9-165">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="75dd9-166">Aprenda a usar De uso general entrada/salida para hacer parpadear un LED</span><span class="sxs-lookup"><span data-stu-id="75dd9-166">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
