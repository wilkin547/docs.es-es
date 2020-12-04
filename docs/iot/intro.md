---
title: Desarrollo de aplicaciones para dispositivos IoT con las bibliotecas de IoT de .NET
description: Obtenga información sobre cómo se puede usar .NET para compilar aplicaciones para dispositivos y escenarios de IoT.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: overview
ms.prod: dotnet
ms.openlocfilehash: c3d05ec5b05780f91404c3c27e91bcd602b0faeb
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594698"
---
# <a name="develop-apps-for-iot-devices-with-the-net-iot-libraries"></a>Desarrollo de aplicaciones para dispositivos IoT con las bibliotecas de IoT de .NET

.NET se ejecuta en diversas plataformas y arquitecturas. Se admiten los paneles de Internet de las cosas (IoT) comunes, como Raspberry PI y Hummingboard. Las aplicaciones de IoT suelen interactuar con hardware especializado, como sensores, convertidores analógicos a digitales y dispositivos LCD. Las bibliotecas de IoT de .NET habilitan estos escenarios.

## <a name="video-overview"></a>Introducción en vídeo

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/IoT-101/Intro-to-IOT-with-NET-Core-1-of-9/player]

## <a name="libraries"></a>Bibliotecas

Las bibliotecas de IoT de .NET se componen de dos paquetes NuGet:

- [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span>
- [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/) <span class="docon docon-navigate-external x-hidden-focus"></span>

### <a name="systemdevicegpio"></a>System.Device.Gpio

`System.Device.Gpio` admite una variedad de protocolos para interactuar con PIN de hardware de bajo nivel para controlar los dispositivos. Entre ellas se incluyen las siguientes:

- E/s de uso general (GPIO)
- Circuito Inter-Integrated (I2C)
- Interfaz de periféricos serie (SPI)
- Modulación de ancho de impulso (PWM)
- Puerto serie

### <a name="iotdevicebindings"></a>Iot.Device.Bindings

El `Iot.Device.Bindings` paquete:

* Contiene [enlaces](https://github.com/dotnet/iot/blob/master/src/devices/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> de dispositivo para simplificar el desarrollo de aplicaciones mediante el ajuste de System. Device. GPIO.
* Es compatible con la comunidad y los enlaces adicionales se agregan continuamente.

Entre los enlaces de dispositivo más usados se incluyen:

- [CharacterLcd-pantalla de caracteres LCD](https://github.com/dotnet/iot/tree/master/src/devices/CharacterLcd)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [SN74HC595: registro de desplazamiento de 8 bits](https://github.com/dotnet/iot/tree/master/src/devices/Sn74hc595)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [BrickPi3](https://github.com/dotnet/iot/tree/master/src/devices/BrickPi3)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [Controlador de Max7219-LED Matrix](https://github.com/dotnet/iot/tree/master/src/devices/Max7219)<span class="docon docon-navigate-external x-hidden-focus"></span>
- [RGBLedMatrix: matriz de LED RGB](https://github.com/dotnet/iot/tree/master/src/devices/RGBLedMatrix)<span class="docon docon-navigate-external x-hidden-focus"></span>

## <a name="supported-operating-systems"></a>Sistemas operativos admitidos

`System.Device.Gpio` es compatible con la mayoría de las versiones de Linux que admiten ARM/ARM64 y Windows 10 IoT Core.

> [!TIP]
> Para Raspberry PI, se recomienda el [sistema operativo Raspberry PI](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) <span class="docon docon-navigate-external x-hidden-focus"></span> (anteriormente Raspbian).  

## <a name="supported-hardware-platforms"></a>Plataformas de hardware compatibles

`System.Device.Gpio` es compatible con la mayoría de las plataformas de un solo panel. Las plataformas recomendadas son Raspberry PI (2 y superior) y Hummingboard. Otras plataformas que se sabe que son compatibles son BeagleBoard y ODROID.

Las plataformas de PC se admiten mediante el uso de un puente USB a SPI/I2C.

> [!IMPORTANT]
> .NET no es compatible con los dispositivos de arquitectura ARMv6, incluidos los dispositivos Raspberry PI Zero y Raspberry PI anteriores a Raspberry pi 2.

## <a name="resources"></a>Recursos

- [Bibliotecas de IOT .net en github](https://github.com/dotnet/iot)<span class="docon docon-navigate-external x-hidden-focus"></span>
