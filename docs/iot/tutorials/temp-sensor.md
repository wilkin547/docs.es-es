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
# <a name="read-environmental-conditions-from-a-sensor"></a><span data-ttu-id="8095b-103">Leer condiciones ambientales de un sensor</span><span class="sxs-lookup"><span data-stu-id="8095b-103">Read environmental conditions from a sensor</span></span>

<span data-ttu-id="8095b-104">Uno de los escenarios más comunes para dispositivos IoT es la detección de condiciones del entorno.</span><span class="sxs-lookup"><span data-stu-id="8095b-104">One of the most common scenarios for IoT devices is detection of environmental conditions.</span></span> <span data-ttu-id="8095b-105">Existen varios sensores disponibles para supervisar la temperatura, la humedad, la presión barométrica y mucho más.</span><span class="sxs-lookup"><span data-stu-id="8095b-105">A variety of sensors are available to monitor temperature, humidity, barometric pressure, and more.</span></span>

<span data-ttu-id="8095b-106">En este tema, usará .NET para leer las condiciones del entorno de un sensor.</span><span class="sxs-lookup"><span data-stu-id="8095b-106">In this topic, you will use .NET to read environmental conditions from a sensor.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8095b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8095b-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="8095b-108">[BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) humedad/presión barométrica/salida del sensor de temperatura</span><span class="sxs-lookup"><span data-stu-id="8095b-108">[BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) humidity/barometric pressure/temperature sensor breakout</span></span>
- <span data-ttu-id="8095b-109">Cables de puente</span><span class="sxs-lookup"><span data-stu-id="8095b-109">Jumper wires</span></span>
- <span data-ttu-id="8095b-110">Placa (opcional)</span><span class="sxs-lookup"><span data-stu-id="8095b-110">Breadboard (optional)</span></span>
- <span data-ttu-id="8095b-111">Placa de salida de Raspberry PI GPIO (opcional)</span><span class="sxs-lookup"><span data-stu-id="8095b-111">Raspberry Pi GPIO breakout board (optional)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!IMPORTANT]
> <span data-ttu-id="8095b-112">Hay muchos fabricantes de sesiones de BME280.</span><span class="sxs-lookup"><span data-stu-id="8095b-112">There are many manufacturers of BME280 breakouts.</span></span> <span data-ttu-id="8095b-113">La mayoría de los diseños son similares y el fabricante no debe tener ninguna diferencia con la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="8095b-113">Most designs are similar, and the manufacturer shouldn't make any difference to the functionality.</span></span> <span data-ttu-id="8095b-114">En este tutorial se intenta tener en cuenta las variaciones.</span><span class="sxs-lookup"><span data-stu-id="8095b-114">This tutorial attempts to account for variations.</span></span> <span data-ttu-id="8095b-115">Asegúrese de que el desglose de BME280 incluye una interfaz de circuito Inter-Integrated (I2C).</span><span class="sxs-lookup"><span data-stu-id="8095b-115">Ensure your BME280 breakout includes an Inter-Integrated Circuit (I2C) interface.</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="8095b-116">Preparar el hardware</span><span class="sxs-lookup"><span data-stu-id="8095b-116">Prepare the hardware</span></span>

<span data-ttu-id="8095b-117">Use los componentes de hardware para compilar el circuito tal y como se muestra en el diagrama siguiente:</span><span class="sxs-lookup"><span data-stu-id="8095b-117">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-bmp280_i2c-thumb.png" alt-text="Un diagrama de Fritz que muestra la conexión de Raspberry PI a BME280" lightbox="../media/rpi-bmp280_i2c.png":::

<span data-ttu-id="8095b-119">A continuación se indican las conexiones desde Raspberry PI al dispositivo de BME280:</span><span class="sxs-lookup"><span data-stu-id="8095b-119">The following are the connections from the Raspberry Pi to the BME280 breakout:</span></span>

- <span data-ttu-id="8095b-120">3,3 v a VIN *o* 3V3 (se muestra en rojo)</span><span class="sxs-lookup"><span data-stu-id="8095b-120">3.3V to VIN *OR* 3V3 (shown in red)</span></span>
- <span data-ttu-id="8095b-121">De fondo a GND (negro)</span><span class="sxs-lookup"><span data-stu-id="8095b-121">Ground to GND (black)</span></span>
- <span data-ttu-id="8095b-122">SDA (GPIO 2) a SDI *o* SDA (azul)</span><span class="sxs-lookup"><span data-stu-id="8095b-122">SDA (GPIO 2) to SDI *OR* SDA (blue)</span></span>
- <span data-ttu-id="8095b-123">SCL (GPIO 3) a SCK *o* SCL (naranja)</span><span class="sxs-lookup"><span data-stu-id="8095b-123">SCL (GPIO 3) to SCK *OR* SCL (orange)</span></span>

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="8095b-124">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="8095b-124">Create the app</span></span>

<span data-ttu-id="8095b-125">Complete los pasos siguientes en el entorno de desarrollo que prefiera:</span><span class="sxs-lookup"><span data-stu-id="8095b-125">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="8095b-126">Cree una nueva aplicación de consola .NET mediante la [CLI de .net](../../core/tools/dotnet-new.md) o [Visual Studio](../../core/tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8095b-126">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="8095b-127">Asígnele el nombre *SensorTutorial*.</span><span class="sxs-lookup"><span data-stu-id="8095b-127">Name it *SensorTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o SensorTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="8095b-128">Reemplace el contenido de *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="8095b-128">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/SensorTutorial/Program.cs" :::

    <span data-ttu-id="8095b-129">En el código anterior:</span><span class="sxs-lookup"><span data-stu-id="8095b-129">In the preceding code:</span></span>

    - <span data-ttu-id="8095b-130">`i2cSettings` se establece en una nueva instancia de `I2cConnectionSettings` .</span><span class="sxs-lookup"><span data-stu-id="8095b-130">`i2cSettings` is set to a new instance of `I2cConnectionSettings`.</span></span> <span data-ttu-id="8095b-131">El constructor establece el `busId` parámetro en 1 y el `deviceAddress` parámetro en `Bme280.DefaultI2cAddress` .</span><span class="sxs-lookup"><span data-stu-id="8095b-131">The constructor sets the `busId` parameter to 1 and the `deviceAddress` parameter to `Bme280.DefaultI2cAddress`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="8095b-132">Algunos fabricantes de BME280 usan el valor de dirección secundaria.</span><span class="sxs-lookup"><span data-stu-id="8095b-132">Some BME280 breakout manufacturers use the secondary address value.</span></span> <span data-ttu-id="8095b-133">Para esos dispositivos, use `Bme280.SecondaryI2cAddress` .</span><span class="sxs-lookup"><span data-stu-id="8095b-133">For those devices, use `Bme280.SecondaryI2cAddress`.</span></span>

    - <span data-ttu-id="8095b-134">Una [declaración Using](../../csharp/whats-new/csharp-8.md#using-declarations) crea una instancia de llamando a `I2cDevice` `I2cDevice.Create` y pasando `i2cSettings` .</span><span class="sxs-lookup"><span data-stu-id="8095b-134">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `I2cDevice` by calling `I2cDevice.Create` and passing in `i2cSettings`.</span></span> <span data-ttu-id="8095b-135">Esto `I2cDevice` representa el bus I2C.</span><span class="sxs-lookup"><span data-stu-id="8095b-135">This `I2cDevice` represents the I2C bus.</span></span> <span data-ttu-id="8095b-136">La `using` declaración garantiza que el objeto se desecha y que los recursos de hardware se liberan correctamente.</span><span class="sxs-lookup"><span data-stu-id="8095b-136">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="8095b-137">Otra `using` declaración crea una instancia de `Bme280` para representar el sensor.</span><span class="sxs-lookup"><span data-stu-id="8095b-137">Another `using` declaration creates an instance of `Bme280` to represent the sensor.</span></span> <span data-ttu-id="8095b-138">`I2cDevice`Se pasa en el constructor.</span><span class="sxs-lookup"><span data-stu-id="8095b-138">The `I2cDevice` is passed in the constructor.</span></span>
    - <span data-ttu-id="8095b-139">El tiempo necesario para que el chip tome medidas con la configuración actual (predeterminada) del chip se recupera mediante una llamada a `GetMeasurementDuration` .</span><span class="sxs-lookup"><span data-stu-id="8095b-139">The time required for the chip to take measurements with the chip's current (default) settings is retrieved by calling `GetMeasurementDuration`.</span></span>
    - <span data-ttu-id="8095b-140">Un `while` bucle se ejecuta indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="8095b-140">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="8095b-141">Cada iteración:</span><span class="sxs-lookup"><span data-stu-id="8095b-141">Each iteration:</span></span>
        1. <span data-ttu-id="8095b-142">Borra la consola.</span><span class="sxs-lookup"><span data-stu-id="8095b-142">Clears the console.</span></span>
        1. <span data-ttu-id="8095b-143">Establece el modo de energía en `Bmx280PowerMode.Forced` .</span><span class="sxs-lookup"><span data-stu-id="8095b-143">Sets the power mode to `Bmx280PowerMode.Forced`.</span></span> <span data-ttu-id="8095b-144">Esto obliga al chip a realizar una medición, almacenar los resultados y, a continuación, entrar en suspensión.</span><span class="sxs-lookup"><span data-stu-id="8095b-144">This forces the chip to perform one measurement, store the results, and then sleep.</span></span>
        1. <span data-ttu-id="8095b-145">Lee los valores de temperatura, presión, humedad y altitud.</span><span class="sxs-lookup"><span data-stu-id="8095b-145">Reads the values for temperature, pressure, humidity, and altitude.</span></span>

            > [!NOTE]
            > <span data-ttu-id="8095b-146">La altitud se calcula mediante el enlace del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8095b-146">Altitude is calculated by the device binding.</span></span> <span data-ttu-id="8095b-147">Esta sobrecarga de `TryReadAltitude` utiliza la presión de nivel de mar media para generar una estimación.</span><span class="sxs-lookup"><span data-stu-id="8095b-147">This overload of `TryReadAltitude` uses mean sea level pressure to generate an estimate.</span></span>

        1. <span data-ttu-id="8095b-148">Escribe las condiciones del entorno actuales en la consola.</span><span class="sxs-lookup"><span data-stu-id="8095b-148">Writes the current environmental conditions to the console.</span></span>
        1. <span data-ttu-id="8095b-149">Suspende 1000 ms.</span><span class="sxs-lookup"><span data-stu-id="8095b-149">Sleeps 1000 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="8095b-150">Ejecute la aplicación en Raspberry PI cambiando al directorio de implementación y ejecutando el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="8095b-150">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./SensorTutorial
    ```

    <span data-ttu-id="8095b-151">Observe la salida del sensor en la consola.</span><span class="sxs-lookup"><span data-stu-id="8095b-151">Observe the sensor output in the console.</span></span>

1. <span data-ttu-id="8095b-152">Para finalizar el programa, presione <kbd>Ctrl + C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="8095b-152">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="8095b-153">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="8095b-153">Congratulations!</span></span> <span data-ttu-id="8095b-154">Ha usado I2C para leer valores de un sensor de presión de temperatura/humedad/barométrica.</span><span class="sxs-lookup"><span data-stu-id="8095b-154">You've used I2C to read values from a temperature/humidity/barometric pressure sensor!</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="8095b-155">Obtención del código fuente</span><span class="sxs-lookup"><span data-stu-id="8095b-155">Get the source code</span></span>

<span data-ttu-id="8095b-156">El origen de este tutorial está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial).</span><span class="sxs-lookup"><span data-stu-id="8095b-156">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8095b-157">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8095b-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8095b-158">Obtenga información sobre cómo mostrar texto en una pantalla LCD</span><span class="sxs-lookup"><span data-stu-id="8095b-158">Learn how to display text on an LCD</span></span>](../tutorials/lcd-display.md)
