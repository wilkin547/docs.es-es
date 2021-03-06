---
title: Desarrollo de aplicaciones para dispositivos IoT con las bibliotecas de IoT de .NET
description: Obtenga información sobre cómo se puede usar .NET para compilar aplicaciones para dispositivos y escenarios de IoT.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: overview
ms.prod: dotnet
ms.openlocfilehash: 13460fdafbfd7ef4e047cb7537e832ae4039c614
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255436"
---
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a><span data-ttu-id="dd3b9-103">Desarrollo de aplicaciones para dispositivos IoT con las bibliotecas de IoT de .NET</span><span class="sxs-lookup"><span data-stu-id="dd3b9-103">Develop apps for IoT devices with the .NET IoT Libraries</span></span>

<span data-ttu-id="dd3b9-104">.NET se ejecuta en diversas plataformas y arquitecturas.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-104">.NET runs on a variety of platforms and architectures.</span></span> <span data-ttu-id="dd3b9-105">Se admiten los paneles de Internet de las cosas (IoT) comunes, como Raspberry PI y Hummingboard.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-105">Common Internet of things (IoT) boards, such as Raspberry Pi and Hummingboard, are supported.</span></span> <span data-ttu-id="dd3b9-106">Las aplicaciones de IoT suelen interactuar con hardware especializado, como sensores, convertidores analógicos a digitales y dispositivos LCD.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-106">IoT apps typically interact with specialized hardware, such as sensors, analog-to-digital converters, and LCD devices.</span></span> <span data-ttu-id="dd3b9-107">Las bibliotecas de IoT de .NET habilitan estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-107">The .NET IoT Libraries enable these scenarios.</span></span>

## <a name="video-overview"></a><span data-ttu-id="dd3b9-108">Introducción en vídeo</span><span class="sxs-lookup"><span data-stu-id="dd3b9-108">Video overview</span></span>

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a><span data-ttu-id="dd3b9-109">Bibliotecas</span><span class="sxs-lookup"><span data-stu-id="dd3b9-109">Libraries</span></span>

<span data-ttu-id="dd3b9-110">Las bibliotecas de IoT de .NET se componen de dos paquetes NuGet:</span><span class="sxs-lookup"><span data-stu-id="dd3b9-110">The .NET IoT Libraries are composed of two NuGet packages:</span></span>

- [<span data-ttu-id="dd3b9-111">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="dd3b9-111">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/)
- [<span data-ttu-id="dd3b9-112">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="dd3b9-112">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/)

### <a name="systemdevicegpio"></a><span data-ttu-id="dd3b9-113">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="dd3b9-113">System.Device.Gpio</span></span>

<span data-ttu-id="dd3b9-114">`System.Device.Gpio` admite una variedad de protocolos para interactuar con PIN de hardware de bajo nivel para controlar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-114">`System.Device.Gpio` supports a variety of protocols for interacting with low-level hardware pins to control devices.</span></span> <span data-ttu-id="dd3b9-115">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd3b9-115">These include:</span></span>

- <span data-ttu-id="dd3b9-116">E/s de uso general (GPIO)</span><span class="sxs-lookup"><span data-stu-id="dd3b9-116">General-purpose I/O (GPIO)</span></span>
- <span data-ttu-id="dd3b9-117">Circuito Inter-Integrated (I2C)</span><span class="sxs-lookup"><span data-stu-id="dd3b9-117">Inter-Integrated Circuit (I2C)</span></span>
- <span data-ttu-id="dd3b9-118">Interfaz de periféricos serie (SPI)</span><span class="sxs-lookup"><span data-stu-id="dd3b9-118">Serial Peripheral Interface (SPI)</span></span>
- <span data-ttu-id="dd3b9-119">Modulación de ancho de impulso (PWM)</span><span class="sxs-lookup"><span data-stu-id="dd3b9-119">Pulse Width Modulation (PWM)</span></span>
- <span data-ttu-id="dd3b9-120">Puerto serie</span><span class="sxs-lookup"><span data-stu-id="dd3b9-120">Serial port</span></span>

### <a name="iotdevicebindings"></a><span data-ttu-id="dd3b9-121">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="dd3b9-121">Iot.Device.Bindings</span></span>

<span data-ttu-id="dd3b9-122">El `Iot.Device.Bindings` paquete:</span><span class="sxs-lookup"><span data-stu-id="dd3b9-122">The `Iot.Device.Bindings` package:</span></span>

* <span data-ttu-id="dd3b9-123">Contiene [enlaces de dispositivo](https://github.com/dotnet/iot/blob/master/src/devices/README.md) para simplificar el desarrollo de aplicaciones mediante el ajuste de System. Device. GPIO.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-123">Contains [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) to streamline app development by wrapping System.Device.Gpio.</span></span>
* <span data-ttu-id="dd3b9-124">Es compatible con la comunidad y los enlaces adicionales se agregan continuamente.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-124">Is community-supported, and additional bindings are added continually.</span></span>

<span data-ttu-id="dd3b9-125">Entre los enlaces de dispositivo más usados se incluyen:</span><span class="sxs-lookup"><span data-stu-id="dd3b9-125">Commonly used device bindings include:</span></span>

- [<span data-ttu-id="dd3b9-126">CharacterLcd-pantalla de caracteres LCD</span><span class="sxs-lookup"><span data-stu-id="dd3b9-126">CharacterLcd - LCD character display</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)
- [<span data-ttu-id="dd3b9-127">SN74HC595: registro de desplazamiento de 8 bits</span><span class="sxs-lookup"><span data-stu-id="dd3b9-127">SN74HC595 - 8-bit shift register</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)
- [<span data-ttu-id="dd3b9-128">BrickPi3</span><span class="sxs-lookup"><span data-stu-id="dd3b9-128">BrickPi3</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)
- [<span data-ttu-id="dd3b9-129">Controlador de Max7219-LED Matrix</span><span class="sxs-lookup"><span data-stu-id="dd3b9-129">Max7219 - LED Matrix driver</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)
- [<span data-ttu-id="dd3b9-130">RGBLedMatrix: matriz de LED RGB</span><span class="sxs-lookup"><span data-stu-id="dd3b9-130">RGBLedMatrix - RGB LED Matrix</span></span>](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)

## <a name="supported-operating-systems"></a><span data-ttu-id="dd3b9-131">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="dd3b9-131">Supported operating systems</span></span>

<span data-ttu-id="dd3b9-132">`System.Device.Gpio` es compatible con la mayoría de las versiones de Linux que admiten ARM/ARM64 y Windows 10 IoT Core.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-132">`System.Device.Gpio` is supported on most versions of Linux that support ARM/ARM64 and Windows 10 IoT Core.</span></span>

> [!TIP]
> <span data-ttu-id="dd3b9-133">Para Raspberry PI, se recomienda el [sistema operativo Raspberry PI](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)  (anteriormente Raspbian).</span><span class="sxs-lookup"><span data-stu-id="dd3b9-133">For Raspberry Pi, [Raspberry Pi OS](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)  (formerly Raspbian) is recommended.</span></span>

## <a name="supported-hardware-platforms"></a><span data-ttu-id="dd3b9-134">Plataformas de hardware compatibles</span><span class="sxs-lookup"><span data-stu-id="dd3b9-134">Supported hardware platforms</span></span>

<span data-ttu-id="dd3b9-135">`System.Device.Gpio` es compatible con la mayoría de las plataformas de un solo panel.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-135">`System.Device.Gpio` is compatible with most single-board platforms.</span></span> <span data-ttu-id="dd3b9-136">Las plataformas recomendadas son Raspberry PI (2 y superior) y Hummingboard.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-136">Recommended platforms are Raspberry Pi (2 and greater) and Hummingboard.</span></span> <span data-ttu-id="dd3b9-137">Otras plataformas que se sabe que son compatibles son BeagleBoard y ODROID.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-137">Other platforms known to be compatible are BeagleBoard and ODROID.</span></span>

<span data-ttu-id="dd3b9-138">Las plataformas de PC se admiten mediante el uso de un puente USB a SPI/I2C.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-138">PC platforms are supported via the use of a USB to SPI/I2C bridge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd3b9-139">.NET no es compatible con los dispositivos de arquitectura ARMv6, incluidos los dispositivos Raspberry PI Zero y Raspberry PI anteriores a Raspberry pi 2.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-139">.NET is not supported on ARMv6 architecture devices, including Raspberry Pi Zero and Raspberry Pi devices prior to Raspberry Pi 2.</span></span>

## <a name="resources"></a><span data-ttu-id="dd3b9-140">Recursos</span><span class="sxs-lookup"><span data-stu-id="dd3b9-140">Resources</span></span>

- [<span data-ttu-id="dd3b9-141">Bibliotecas de IoT .NET en github</span><span class="sxs-lookup"><span data-stu-id="dd3b9-141">.NET IoT Libraries on Github</span></span>](https://github.com/dotnet/iot)
