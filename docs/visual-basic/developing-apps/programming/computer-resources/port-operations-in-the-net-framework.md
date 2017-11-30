---
title: Operaciones de puertos en .NET Framework con Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8db016461ea204eaf349a2c588670a237c9e583b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a><span data-ttu-id="11620-102">Operaciones de puertos en .NET Framework con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11620-102">Port Operations in the .NET Framework with Visual Basic</span></span>
<span data-ttu-id="11620-103">Puede acceder a los puertos serie del equipo mediante las clases [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] del espacio de nombres <xref:System.IO.Ports?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11620-103">You can access your computer's serial ports through the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="11620-104">La clase más importante, <xref:System.IO.Ports.SerialPort>, proporciona un marco de trabajo para la E/S sincrónica y orientada a eventos, el acceso a los estados de punto de conexión e interrupción y el acceso a las propiedades del controlador serie.</span><span class="sxs-lookup"><span data-stu-id="11620-104">The most important class, <xref:System.IO.Ports.SerialPort>, provides a framework for synchronous and event-driven I/O, access to pin and break states, and access to serial driver properties.</span></span> <span data-ttu-id="11620-105">Se puede encapsular en un objeto <xref:System.IO.Stream>, al que se puede acceder a través de la propiedad <xref:System.IO.Ports.SerialPort.BaseStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="11620-105">It can be wrapped in a <xref:System.IO.Stream> object, accessible through the <xref:System.IO.Ports.SerialPort.BaseStream%2A> property.</span></span> <span data-ttu-id="11620-106">Al encapsular <xref:System.IO.Ports.SerialPort> en un objeto <xref:System.IO.Stream> se puede acceder al puerto serie mediante las clases que usan flujos.</span><span class="sxs-lookup"><span data-stu-id="11620-106">Wrapping <xref:System.IO.Ports.SerialPort> in a <xref:System.IO.Stream> object allows the serial port to be accessed by classes that use streams.</span></span> <span data-ttu-id="11620-107">El espacio de nombres incluye enumeraciones que simplifican el control de los puertos serie.</span><span class="sxs-lookup"><span data-stu-id="11620-107">The namespace includes enumerations that simplify the control of serial ports.</span></span>  
  
 <span data-ttu-id="11620-108">La forma más sencilla de crear un objeto <xref:System.IO.Ports.SerialPort> es a través del método <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="11620-108">The simplest way to create a <xref:System.IO.Ports.SerialPort> object is through the <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11620-109">No se pueden usar clases [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para acceder directamente a otros tipos de puertos, como puertos paralelos, puertos USB, etc.</span><span class="sxs-lookup"><span data-stu-id="11620-109">You cannot use [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes to directly access other types of ports, such as parallel ports, USB ports, and so on.</span></span>  
  
## <a name="enumerations"></a><span data-ttu-id="11620-110">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="11620-110">Enumerations</span></span>  
 <span data-ttu-id="11620-111">En esta tabla se enumeran y se describen las enumeraciones principales usadas para acceder a un puerto serie:</span><span class="sxs-lookup"><span data-stu-id="11620-111">This table lists and describes the main enumerations used for accessing a serial port:</span></span>  
  
|<span data-ttu-id="11620-112">Enumeración</span><span class="sxs-lookup"><span data-stu-id="11620-112">Enumeration</span></span>|<span data-ttu-id="11620-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="11620-113">Description</span></span>|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|<span data-ttu-id="11620-114">Especifica el protocolo de control usado para establecer una comunicación de puerto serie para un objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="11620-114">Specifies the control protocol used in establishing a serial port communication for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.Parity>|<span data-ttu-id="11620-115">Especifica el bit de paridad para un objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="11620-115">Specifies the parity bit for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialData>|<span data-ttu-id="11620-116">Especifica el tipo de carácter que se ha recibido en el puerto serie del objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="11620-116">Specifies the type of character that was received on the serial port of the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialError>|<span data-ttu-id="11620-117">Especifica los errores que se producen en el objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="11620-117">Specifies errors that occur on the <xref:System.IO.Ports.SerialPort> object</span></span>|  
|<xref:System.IO.Ports.SerialPinChange>|<span data-ttu-id="11620-118">Especifica el tipo de cambio producido en el objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="11620-118">Specifies the type of change that occurred on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.StopBits>|<span data-ttu-id="11620-119">Especifica el número de bits de parada usados en el objeto <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="11620-119">Specifies the number of stop bits used on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11620-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="11620-120">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 [<span data-ttu-id="11620-121">Acceso a los puertos del equipo</span><span class="sxs-lookup"><span data-stu-id="11620-121">Accessing the Computer's Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
