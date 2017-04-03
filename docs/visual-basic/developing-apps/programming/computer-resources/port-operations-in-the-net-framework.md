---
title: Operaciones de puertos en .NET Framework con Visual Basic | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 61b91fe5f3bb016bace838b9eeabb1a59190bfe9
ms.lasthandoff: 03/13/2017

---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a>Operaciones de puertos en .NET Framework con Visual Basic
Puede acceder a los puertos serie del equipo mediante las clases [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] del espacio de nombres <xref:System.IO.Ports?displayProperty=fullName>. La clase más importante, <xref:System.IO.Ports.SerialPort>, proporciona un marco de trabajo para la E/S sincrónica y orientada a eventos, el acceso a los estados de punto de conexión e interrupción y el acceso a las propiedades del controlador serie. Se puede encapsular en un objeto <xref:System.IO.Stream>, accesible mediante la propiedad <xref:System.IO.Ports.SerialPort.BaseStream%2A>. El encapsulamiento de <xref:System.IO.Ports.SerialPort> en un objeto <xref:System.IO.Stream> permite que las clases que usan flujos accedan al puerto serie. El espacio de nombres incluye enumeraciones que simplifican el control de los puertos serie.  
  
 La manera más sencilla de crear un objeto <xref:System.IO.Ports.SerialPort> es mediante el método <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
> [!NOTE]
>  No se pueden usar clases [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] para acceder directamente a otros tipos de puertos, como puertos paralelos, puertos USB, etc.  
  
## <a name="enumerations"></a>Enumeraciones  
 En esta tabla se enumeran y se describen las enumeraciones principales usadas para acceder a un puerto serie:  
  
|Enumeración|Descripción|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|Especifica el protocolo de control usado para establecer una comunicación de puerto serie para un objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.Parity>|Especifica el bit de paridad para un objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialData>|Especifica el tipo de carácter que se ha recibido en el puerto serie del objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialError>|Especifica los errores que se producen en el objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialPinChange>|Especifica el tipo de cambio que se ha producido en el objeto <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.StopBits>|Especifica el número de bits de parada usados en el objeto <xref:System.IO.Ports.SerialPort>.|  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Acceso a los puertos del equipo](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
