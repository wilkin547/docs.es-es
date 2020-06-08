---
title: Operaciones de puertos en .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
ms.openlocfilehash: 0ef0b8a7aec40603185d227d972cea655fd238c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360142"
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a>Operaciones de puertos en .NET Framework con Visual Basic

Puede acceder a los puertos serie del equipo mediante las clases de .NET Framework del espacio de nombres <xref:System.IO.Ports?displayProperty=nameWithType>. La clase más importante, <xref:System.IO.Ports.SerialPort>, proporciona un marco de trabajo para la E/S sincrónica y orientada a eventos, el acceso a los estados de punto de conexión e interrupción y el acceso a las propiedades del controlador serie. Se puede encapsular en un objeto <xref:System.IO.Stream>, al que se puede acceder a través de la propiedad <xref:System.IO.Ports.SerialPort.BaseStream>. Al encapsular <xref:System.IO.Ports.SerialPort> en un objeto <xref:System.IO.Stream> se puede acceder al puerto serie mediante las clases que usan flujos. El espacio de nombres incluye enumeraciones que simplifican el control de los puertos serie.

La forma más sencilla de crear un objeto <xref:System.IO.Ports.SerialPort> es a través del método <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.

> [!NOTE]
> No se pueden usar clases de .NET Framework para acceder directamente a otros tipos de puertos, como puertos paralelos, puertos USB, etc.

## <a name="enumerations"></a>Enumeraciones

En esta tabla se enumeran y se describen las enumeraciones principales usadas para acceder a un puerto serie:

|Enumeración|Description|
|---|---|
|<xref:System.IO.Ports.Handshake>|Especifica el protocolo de control usado para establecer una comunicación de puerto serie para un objeto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.Parity>|Especifica el bit de paridad para un objeto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialData>|Especifica el tipo de carácter que se ha recibido en el puerto serie del objeto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialError>|Especifica los errores que se producen en el objeto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialPinChange>|Especifica el tipo de cambio producido en el objeto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.StopBits>|Especifica el número de bits de parada usados en el objeto <xref:System.IO.Ports.SerialPort>.|

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [Acceso a los puertos del equipo](accessing-the-computer-s-ports.md)
