---
title: "Operaciones de puertos en .NET Framework con Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "puertos, Visual Basic"
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Operaciones de puertos en .NET Framework con Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede tener acceso a los puertos serie de su equipo a través de las clases de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] que contiene el espacio de nombres <xref:System.IO.Ports?displayProperty=fullName>.  La clase más importante, <xref:System.IO.Ports.SerialPort>, proporciona un marco de trabajo para la E\/S sincrónica y orientada a eventos, el acceso a los estados de punto de conexión e interrupción y el acceso a las propiedades del controlador serie.  Se puede ajustar en un objeto <xref:System.IO.Stream>, accesible a través de la propiedad <xref:System.IO.Ports.SerialPort.BaseStream%2A>.  Ajustar <xref:System.IO.Ports.SerialPort> en un objeto <xref:System.IO.Stream> permite que las clases que utilizan secuencias tengan acceso al puerto serie.  El espacio de nombres incluye enumeraciones que simplifican el control de los puertos serie.  
  
 La manera más simple de crear un objeto <xref:System.IO.Ports.SerialPort> es a través del método <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
> [!NOTE]
>  No puede usar las clases de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] para tener acceso directamente a otros tipos de puertos, como puertos paralelos, puertos USB, etc.  
  
## Enumeraciones  
 Esta tabla muestra y describe las enumeraciones principales utilizadas para tener acceso a un puerto serie:  
  
|||  
|-|-|  
|Enumeración|Descripción|  
|<xref:System.IO.Ports.Handshake>|Especifica el protocolo de control utilizado para establecer una comunicación del puerto serie para un objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.Parity>|Especifica el bit de paridad para un objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialData>|Especifica el tipo de carácter que se recibió en el puerto serie del objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialError>|Especifica errores que aparecen en el objeto <xref:System.IO.Ports.SerialPort>|  
|<xref:System.IO.Ports.SerialPinChange>|Especifica el tipo de cambio que apareció en el objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.StopBits>|Especifica el número de bits de parada utilizado en el objeto <xref:System.IO.Ports.SerialPort>.|  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Acceso a los puertos del equipo](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)