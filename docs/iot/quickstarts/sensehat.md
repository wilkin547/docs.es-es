---
title: 'Inicio rápido: uso de .NET para impulsar un sombrero de sentido de Raspberry PI'
description: Comience a trabajar con las bibliotecas de IoT de .NET en 5 minutos con una detección HAT, una placa de complemento para Raspberry PI.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: quickstart
ms.prod: dotnet
ms.openlocfilehash: 28d6650187bbf7b9ce91516f4da4d09b114c904a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259705"
---
# <a name="quickstart---use-net-to-drive-a-raspberry-pi-sense-hat"></a><span data-ttu-id="05123-103">Inicio rápido: uso de .NET para impulsar un sombrero de sentido de Raspberry PI</span><span class="sxs-lookup"><span data-stu-id="05123-103">Quickstart - Use .NET to drive a Raspberry Pi Sense HAT</span></span>

<span data-ttu-id="05123-104">El [sensor](https://www.raspberrypi.org/products/sense-hat/) de Raspberry PI (**H** hardware **a** ttached en **T** OP) es un panel complementario para Raspberry PI.</span><span class="sxs-lookup"><span data-stu-id="05123-104">The Raspberry Pi [Sense HAT](https://www.raspberrypi.org/products/sense-hat/) (**H** ardware **A** ttached on **T** op) is an add-on board for Raspberry Pi.</span></span> <span data-ttu-id="05123-105">El sombrero de detección está equipado con una matriz de LED RGB de 8 × 8, un joystick de cinco botones e incluye los sensores siguientes:</span><span class="sxs-lookup"><span data-stu-id="05123-105">The Sense HAT is equipped with an 8×8 RGB LED matrix, a five-button joystick, and includes the following sensors:</span></span>

- <span data-ttu-id="05123-106">Giroscopio</span><span class="sxs-lookup"><span data-stu-id="05123-106">Gyroscope</span></span>
- <span data-ttu-id="05123-107">Acelerómetro</span><span class="sxs-lookup"><span data-stu-id="05123-107">Accelerometer</span></span>
- <span data-ttu-id="05123-108">Magnetómetro</span><span class="sxs-lookup"><span data-stu-id="05123-108">Magnetometer</span></span>
- <span data-ttu-id="05123-109">Temperatura</span><span class="sxs-lookup"><span data-stu-id="05123-109">Temperature</span></span>
- <span data-ttu-id="05123-110">Presión barométrica</span><span class="sxs-lookup"><span data-stu-id="05123-110">Barometric pressure</span></span>
- <span data-ttu-id="05123-111">Humedad</span><span class="sxs-lookup"><span data-stu-id="05123-111">Humidity</span></span>

<span data-ttu-id="05123-112">Esta guía de inicio rápido usa .NET para recuperar los valores del sensor desde el sombrero de detección, responder a la entrada del joystick y controlar la matriz de LED.</span><span class="sxs-lookup"><span data-stu-id="05123-112">This quickstart uses .NET to retrieve sensor values from the Sense HAT, respond to joystick input, and drive the LED matrix.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05123-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="05123-113">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="05123-114">Detección HAT</span><span class="sxs-lookup"><span data-stu-id="05123-114">Sense HAT</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="run-the-quickstart"></a><span data-ttu-id="05123-115">Ejecutar la guía de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="05123-115">Run the quickstart</span></span>

<span data-ttu-id="05123-116">Adjunte el sombrero de detección a su Raspberry PI.</span><span class="sxs-lookup"><span data-stu-id="05123-116">Attach the Sense HAT to your Raspberry Pi.</span></span> <span data-ttu-id="05123-117">En un símbolo del sistema de bash en Raspberry PI (local o remoto), ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="05123-117">From a Bash prompt on the Raspberry Pi (local or remote), run the following command:</span></span>

```bash
. <(wget -q -O - https://aka.ms/dotnet-iot-sensehat-quickstart)
```

<span data-ttu-id="05123-118">El comando descarga y ejecuta un script.</span><span class="sxs-lookup"><span data-stu-id="05123-118">The command downloads and runs a script.</span></span> <span data-ttu-id="05123-119">El script:</span><span class="sxs-lookup"><span data-stu-id="05123-119">The script:</span></span>

- <span data-ttu-id="05123-120">Instala el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="05123-120">Installs the .NET SDK.</span></span>
- <span data-ttu-id="05123-121">Clona un repositorio de GitHub que incluye el proyecto de inicio rápido de Sense HAT.</span><span class="sxs-lookup"><span data-stu-id="05123-121">Clones a GitHub repository that includes the Sense HAT quickstart project.</span></span>
- <span data-ttu-id="05123-122">Compila el proyecto.</span><span class="sxs-lookup"><span data-stu-id="05123-122">Builds the project.</span></span>
- <span data-ttu-id="05123-123">Ejecuta el proyecto.</span><span class="sxs-lookup"><span data-stu-id="05123-123">Runs the project.</span></span>

<span data-ttu-id="05123-124">Observe el resultado de la consola a medida que se muestran los datos del sensor.</span><span class="sxs-lookup"><span data-stu-id="05123-124">Observe the console output as sensor data is displayed.</span></span> <span data-ttu-id="05123-125">La matriz LED muestra un píxel amarillo en un campo de color azul.</span><span class="sxs-lookup"><span data-stu-id="05123-125">The LED matrix displays a yellow pixel on a field of blue.</span></span> <span data-ttu-id="05123-126">Al mantener el joystick en cualquier dirección, se mueve el píxel amarillo en esa dirección.</span><span class="sxs-lookup"><span data-stu-id="05123-126">Holding the joystick in any direction moves the yellow pixel in that direction.</span></span> <span data-ttu-id="05123-127">Al hacer clic en el botón central joystick, el fondo cambia de azul a rojo.</span><span class="sxs-lookup"><span data-stu-id="05123-127">Clicking the center joystick button causes the background to switch from blue to red.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="05123-128">Obtención del código fuente</span><span class="sxs-lookup"><span data-stu-id="05123-128">Get the source code</span></span>

<span data-ttu-id="05123-129">El origen de esta guía de inicio rápido está [disponible en github](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart).</span><span class="sxs-lookup"><span data-stu-id="05123-129">The source for this quickstart is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart).</span></span>

## <a name="next-steps"></a><span data-ttu-id="05123-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="05123-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05123-131">Aprenda a usar De uso general entrada/salida para hacer parpadear un LED</span><span class="sxs-lookup"><span data-stu-id="05123-131">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
