---
title: Mostrar texto en una pantalla LCD
description: Obtenga información sobre cómo mostrar caracteres en una pantalla de cristal líquido con las bibliotecas de IoT de .NET.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 005b40a7d9f46b84fcd90541248f5f4fd243e612
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255556"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="display-text-on-an-lcd"></a><span data-ttu-id="84b2b-103">Mostrar texto en una pantalla LCD</span><span class="sxs-lookup"><span data-stu-id="84b2b-103">Display text on an LCD</span></span>

<span data-ttu-id="84b2b-104">Las pantallas de caracteres LCD son útiles para mostrar información sin necesidad de un monitor externo.</span><span class="sxs-lookup"><span data-stu-id="84b2b-104">LCD character displays are useful for displaying information without the need for an external monitor.</span></span> <span data-ttu-id="84b2b-105">Las pantallas de caracteres LCD comunes se pueden conectar directamente a los pin de GPIO, pero este enfoque requiere el uso de hasta 10 clavijas de GPIO.</span><span class="sxs-lookup"><span data-stu-id="84b2b-105">Common LCD character displays can be connected directly to the GPIO pins, but such an approach requires the use of up to 10 GPIO pins.</span></span> <span data-ttu-id="84b2b-106">En el caso de los escenarios que requieren la conexión a una combinación de dispositivos, la desvotación de forma que gran parte del encabezado GPIO a una presentación de caracteres no suele ser práctica.</span><span class="sxs-lookup"><span data-stu-id="84b2b-106">For scenarios that require connecting to a combination of devices, devoting so much of the GPIO header to a character display is often impractical.</span></span>

<span data-ttu-id="84b2b-107">Muchos fabricantes venden el carácter LCD 20x4 con un expansor de GPIO integrado.</span><span class="sxs-lookup"><span data-stu-id="84b2b-107">Many manufacturers sell 20x4 LCD character displays with an integrated GPIO expander.</span></span> <span data-ttu-id="84b2b-108">La visualización de caracteres se conecta directamente al expansor de GPIO, que luego se conecta a Raspberry PI a través del protocolo serie de Inter-Integrated circuito (I2C).</span><span class="sxs-lookup"><span data-stu-id="84b2b-108">The character display connects directly to the GPIO expander, which then connects to the Raspberry Pi via the Inter-Integrated Circuit (I2C) serial protocol.</span></span>

<span data-ttu-id="84b2b-109">En este tema, usará .NET para mostrar texto en una pantalla de caracteres LCD mediante un expansor de I2C GPIO.</span><span class="sxs-lookup"><span data-stu-id="84b2b-109">In this topic, you will use .NET to display text on an LCD character display using an I2C GPIO expander.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="84b2b-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="84b2b-110">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [<span data-ttu-id="84b2b-111">Presentación de caracteres LCD 20x4 con la interfaz I2C</span><span class="sxs-lookup"><span data-stu-id="84b2b-111">20x4 LCD Character Display with I2C interface</span></span>](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c)
- <span data-ttu-id="84b2b-112">Cables de puente</span><span class="sxs-lookup"><span data-stu-id="84b2b-112">Jumper wires</span></span>
- <span data-ttu-id="84b2b-113">Placa (opcional/recomendado)</span><span class="sxs-lookup"><span data-stu-id="84b2b-113">Breadboard (optional/recommended)</span></span>
- <span data-ttu-id="84b2b-114">Placa de salida de Raspberry PI GPIO (opcional/recomendado)</span><span class="sxs-lookup"><span data-stu-id="84b2b-114">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!NOTE]
> <span data-ttu-id="84b2b-115">Hay muchos fabricantes de pantallas de caracteres LCD.</span><span class="sxs-lookup"><span data-stu-id="84b2b-115">There are many manufacturers of LCD character displays.</span></span> <span data-ttu-id="84b2b-116">La mayoría de los diseños son idénticos y el fabricante no debe tener ninguna diferencia con la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="84b2b-116">Most designs are identical, and the manufacturer shouldn't make any difference to the functionality.</span></span> <span data-ttu-id="84b2b-117">Como referencia, este tutorial se desarrolló con el [LCD2004 del descubierto](https://www.sunfounder.com/lcd2004-module.html).</span><span class="sxs-lookup"><span data-stu-id="84b2b-117">For reference, this tutorial was developed with the [SunFounder LCD2004](https://www.sunfounder.com/lcd2004-module.html).</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="84b2b-118">Preparar el hardware</span><span class="sxs-lookup"><span data-stu-id="84b2b-118">Prepare the hardware</span></span>

<span data-ttu-id="84b2b-119">Use cables de puente para conectar los cuatro PIN del expansor de I2C GPIO al Raspberry PI como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="84b2b-119">Use jumper wires to connect the four pins on the I2C GPIO expander to the Raspberry Pi as follows:</span></span>

- <span data-ttu-id="84b2b-120">GND a suelo</span><span class="sxs-lookup"><span data-stu-id="84b2b-120">GND to ground</span></span>
- <span data-ttu-id="84b2b-121">VCC a 5 v</span><span class="sxs-lookup"><span data-stu-id="84b2b-121">VCC to 5V</span></span>
- <span data-ttu-id="84b2b-122">SDA a SDA (GPIO 2)</span><span class="sxs-lookup"><span data-stu-id="84b2b-122">SDA to SDA (GPIO 2)</span></span>
- <span data-ttu-id="84b2b-123">SCL a SCL (GPIO 3)</span><span class="sxs-lookup"><span data-stu-id="84b2b-123">SCL to SCL (GPIO 3)</span></span>

<span data-ttu-id="84b2b-124">Consulte las siguientes figuras según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="84b2b-124">Refer to the following figures as needed:</span></span>

| <span data-ttu-id="84b2b-125">Interfaz I2C (parte posterior de la pantalla)</span><span class="sxs-lookup"><span data-stu-id="84b2b-125">I2C interface (back of display)</span></span> | <span data-ttu-id="84b2b-126">Raspberry PI GPIO</span><span class="sxs-lookup"><span data-stu-id="84b2b-126">Raspberry Pi GPIO</span></span> |
|---------------------------------|-------------------|
| :::image type="content" source="../media/character-display-i2c-thumb.png" alt-text="Imagen de la parte posterior de la presentación de caracteres que muestra el expansor de I2C GPIO." lightbox="../media/character-display-i2c.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Diagrama que muestra el pines del encabezado GPIO de Raspberry PI. Image de Raspberry PI Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br /><span data-ttu-id="84b2b-129">[Image de Raspberry PI Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span><span class="sxs-lookup"><span data-stu-id="84b2b-129">[Image courtesy Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span></span>
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="84b2b-130">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="84b2b-130">Create the app</span></span>

<span data-ttu-id="84b2b-131">Complete los pasos siguientes en el entorno de desarrollo que prefiera:</span><span class="sxs-lookup"><span data-stu-id="84b2b-131">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="84b2b-132">Cree una nueva aplicación de consola .NET mediante la [CLI de .net](../../core/tools/dotnet-new.md) o [Visual Studio](../../core/tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="84b2b-132">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="84b2b-133">Asígnele el nombre *LcdTutorial*.</span><span class="sxs-lookup"><span data-stu-id="84b2b-133">Name it *LcdTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o LcdTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="84b2b-134">Reemplace el contenido de *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="84b2b-134">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/LcdTutorial/Program.cs" :::

    <span data-ttu-id="84b2b-135">En el código anterior:</span><span class="sxs-lookup"><span data-stu-id="84b2b-135">In the preceding code:</span></span>

    - <span data-ttu-id="84b2b-136">Una [declaración Using](../../csharp/whats-new/csharp-8.md#using-declarations) crea una instancia de llamando a `I2cDevice` `I2cDevice.Create` y pasando un nuevo `I2cConnectionSettings` con los `busId` parámetros y `deviceAddress` .</span><span class="sxs-lookup"><span data-stu-id="84b2b-136">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `I2cDevice` by calling `I2cDevice.Create` and passing in a new `I2cConnectionSettings` with the `busId` and `deviceAddress` parameters.</span></span> <span data-ttu-id="84b2b-137">Esto `I2cDevice` representa el bus I2C.</span><span class="sxs-lookup"><span data-stu-id="84b2b-137">This `I2cDevice` represents the I2C bus.</span></span> <span data-ttu-id="84b2b-138">La `using` declaración garantiza que el objeto se desecha y que los recursos de hardware se liberan correctamente.</span><span class="sxs-lookup"><span data-stu-id="84b2b-138">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>

        > [!WARNING]
        > <span data-ttu-id="84b2b-139">La dirección del dispositivo para el expansor de GPIO depende del chip usado por el fabricante.</span><span class="sxs-lookup"><span data-stu-id="84b2b-139">The device address for the GPIO expander depends on the chip used by the manufacturer.</span></span> <span data-ttu-id="84b2b-140">Los ampliadores de GPIO equipados con un PCF8574 usan la dirección, mientras que las que usan los `0x27` chips de PCF8574A usan `0x3F` .</span><span class="sxs-lookup"><span data-stu-id="84b2b-140">GPIO expanders equipped with a PCF8574 use the address `0x27`, while those using PCF8574A chips use `0x3F`.</span></span> <span data-ttu-id="84b2b-141">Consulte la documentación de su LCD.</span><span class="sxs-lookup"><span data-stu-id="84b2b-141">Consult your LCD's documentation.</span></span>

    - <span data-ttu-id="84b2b-142">Otra `using` declaración crea una instancia de `Pcf8574` y pasa `I2cDevice` en el constructor.</span><span class="sxs-lookup"><span data-stu-id="84b2b-142">Another `using` declaration creates an instance of `Pcf8574` and passes the `I2cDevice` into the constructor.</span></span> <span data-ttu-id="84b2b-143">Esta instancia representa el expansor del GPIO.</span><span class="sxs-lookup"><span data-stu-id="84b2b-143">This instance represents the GPIO expander.</span></span>
    - <span data-ttu-id="84b2b-144">Otra `using` declaración crea una instancia de `Lcd2004` para representar la presentación.</span><span class="sxs-lookup"><span data-stu-id="84b2b-144">Another `using` declaration creates an instance of `Lcd2004` to represent the display.</span></span> <span data-ttu-id="84b2b-145">Se pasan varios parámetros al constructor que describen la configuración que se va a usar para comunicarse con el expansor de GPIO.</span><span class="sxs-lookup"><span data-stu-id="84b2b-145">Several parameters are passed to the constructor describing the settings to use to communicate with the GPIO expander.</span></span> <span data-ttu-id="84b2b-146">El expansor de GPIO se pasa como `controller` parámetro.</span><span class="sxs-lookup"><span data-stu-id="84b2b-146">The GPIO expander is passed as the `controller` parameter.</span></span>
    - <span data-ttu-id="84b2b-147">Un `while` bucle se ejecuta indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="84b2b-147">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="84b2b-148">Cada iteración:</span><span class="sxs-lookup"><span data-stu-id="84b2b-148">Each iteration:</span></span>
        1. <span data-ttu-id="84b2b-149">Borra la pantalla.</span><span class="sxs-lookup"><span data-stu-id="84b2b-149">Clears the display.</span></span>
        1. <span data-ttu-id="84b2b-150">Establece la posición del cursor en la primera posición de la línea actual.</span><span class="sxs-lookup"><span data-stu-id="84b2b-150">Sets the cursor position to the first position on the current line.</span></span>
        1. <span data-ttu-id="84b2b-151">Escribe la hora actual en la presentación en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="84b2b-151">Writes the current time to the display at the current cursor position.</span></span>
        1. <span data-ttu-id="84b2b-152">Procesa una iteración en el contador de línea actual.</span><span class="sxs-lookup"><span data-stu-id="84b2b-152">Iterates the current line counter.</span></span>
        1. <span data-ttu-id="84b2b-153">Suspende 1000 ms.</span><span class="sxs-lookup"><span data-stu-id="84b2b-153">Sleeps 1000 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="84b2b-154">Ejecute la aplicación en Raspberry PI cambiando al directorio de implementación y ejecutando el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="84b2b-154">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./LcdTutorial
    ```

    <span data-ttu-id="84b2b-155">Observe la pantalla del carácter LCD a medida que se muestra la hora actual en cada línea.</span><span class="sxs-lookup"><span data-stu-id="84b2b-155">Observe the LCD character display as the current time displays on each line.</span></span>

    > [!TIP]
    > <span data-ttu-id="84b2b-156">Si la pantalla está encendida, pero no ve ningún texto, intente ajustar el contraste en la parte posterior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="84b2b-156">If the display is lit but you don't see any text, try adjusting the contrast dial on the back of the display.</span></span>

1. <span data-ttu-id="84b2b-157">Para finalizar el programa, presione <kbd>Ctrl + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="84b2b-157">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="84b2b-158">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="84b2b-158">Congratulations!</span></span> <span data-ttu-id="84b2b-159">Ha mostrado texto en un LCD con un expansor y un expansor de GPIO.</span><span class="sxs-lookup"><span data-stu-id="84b2b-159">You've displayed text on an LCD using a I2C and a GPIO expander!</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="84b2b-160">Obtención del código fuente</span><span class="sxs-lookup"><span data-stu-id="84b2b-160">Get the source code</span></span>

<span data-ttu-id="84b2b-161">El origen de este tutorial está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial).</span><span class="sxs-lookup"><span data-stu-id="84b2b-161">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial).</span></span>

## <a name="next-steps"></a><span data-ttu-id="84b2b-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="84b2b-162">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="84b2b-163">Aprenda a usar De uso general entrada/salida para hacer parpadear un LED</span><span class="sxs-lookup"><span data-stu-id="84b2b-163">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
