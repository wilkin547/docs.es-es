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
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a><span data-ttu-id="eaf9e-102">Operaciones de puertos en .NET Framework con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eaf9e-102">Port Operations in the .NET Framework with Visual Basic</span></span>

<span data-ttu-id="eaf9e-103">Puede acceder a los puertos serie del equipo mediante las clases de .NET Framework del espacio de nombres <xref:System.IO.Ports?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-103">You can access your computer's serial ports through the .NET Framework classes in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="eaf9e-104">La clase más importante, <xref:System.IO.Ports.SerialPort>, proporciona un marco de trabajo para la E/S sincrónica y orientada a eventos, el acceso a los estados de punto de conexión e interrupción y el acceso a las propiedades del controlador serie.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-104">The most important class, <xref:System.IO.Ports.SerialPort>, provides a framework for synchronous and event-driven I/O, access to pin and break states, and access to serial driver properties.</span></span> <span data-ttu-id="eaf9e-105">Se puede encapsular en un objeto <xref:System.IO.Stream>, al que se puede acceder a través de la propiedad <xref:System.IO.Ports.SerialPort.BaseStream>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-105">It can be wrapped in a <xref:System.IO.Stream> object, accessible through the <xref:System.IO.Ports.SerialPort.BaseStream> property.</span></span> <span data-ttu-id="eaf9e-106">Al encapsular <xref:System.IO.Ports.SerialPort> en un objeto <xref:System.IO.Stream> se puede acceder al puerto serie mediante las clases que usan flujos.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-106">Wrapping <xref:System.IO.Ports.SerialPort> in a <xref:System.IO.Stream> object allows the serial port to be accessed by classes that use streams.</span></span> <span data-ttu-id="eaf9e-107">El espacio de nombres incluye enumeraciones que simplifican el control de los puertos serie.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-107">The namespace includes enumerations that simplify the control of serial ports.</span></span>

<span data-ttu-id="eaf9e-108">La forma más sencilla de crear un objeto <xref:System.IO.Ports.SerialPort> es a través del método <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-108">The simplest way to create a <xref:System.IO.Ports.SerialPort> object is through the <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> method.</span></span>

> [!NOTE]
> <span data-ttu-id="eaf9e-109">No se pueden usar clases de .NET Framework para acceder directamente a otros tipos de puertos, como puertos paralelos, puertos USB, etc.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-109">You cannot use .NET Framework classes to directly access other types of ports, such as parallel ports, USB ports, and so on.</span></span>

## <a name="enumerations"></a><span data-ttu-id="eaf9e-110">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="eaf9e-110">Enumerations</span></span>

<span data-ttu-id="eaf9e-111">En esta tabla se enumeran y se describen las enumeraciones principales usadas para acceder a un puerto serie:</span><span class="sxs-lookup"><span data-stu-id="eaf9e-111">This table lists and describes the main enumerations used for accessing a serial port:</span></span>

|<span data-ttu-id="eaf9e-112">Enumeración</span><span class="sxs-lookup"><span data-stu-id="eaf9e-112">Enumeration</span></span>|<span data-ttu-id="eaf9e-113">Description</span><span class="sxs-lookup"><span data-stu-id="eaf9e-113">Description</span></span>|
|---|---|
|<xref:System.IO.Ports.Handshake>|<span data-ttu-id="eaf9e-114">Especifica el protocolo de control usado para establecer una comunicación de puerto serie para un objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-114">Specifies the control protocol used in establishing a serial port communication for a <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.Parity>|<span data-ttu-id="eaf9e-115">Especifica el bit de paridad para un objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-115">Specifies the parity bit for a <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.SerialData>|<span data-ttu-id="eaf9e-116">Especifica el tipo de carácter que se ha recibido en el puerto serie del objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-116">Specifies the type of character that was received on the serial port of the <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.SerialError>|<span data-ttu-id="eaf9e-117">Especifica los errores que se producen en el objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-117">Specifies errors that occur on the <xref:System.IO.Ports.SerialPort> object</span></span>|
|<xref:System.IO.Ports.SerialPinChange>|<span data-ttu-id="eaf9e-118">Especifica el tipo de cambio producido en el objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-118">Specifies the type of change that occurred on the <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.StopBits>|<span data-ttu-id="eaf9e-119">Especifica el número de bits de parada usados en el objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-119">Specifies the number of stop bits used on the <xref:System.IO.Ports.SerialPort> object.</span></span>|

## <a name="see-also"></a><span data-ttu-id="eaf9e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="eaf9e-120">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [<span data-ttu-id="eaf9e-121">Acceso a los puertos del equipo</span><span class="sxs-lookup"><span data-stu-id="eaf9e-121">Accessing the Computer's Ports</span></span>](accessing-the-computer-s-ports.md)
