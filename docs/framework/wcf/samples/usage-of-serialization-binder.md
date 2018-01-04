---
title: "Uso del enlazador de serialización"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be6ce62722c0d1bd18122496312c3a55241a8fbb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="usage-of-serialization-binder"></a>Uso del enlazador de serialización
Este ejemplo muestra cómo utilizar <xref:System.Runtime.Serialization.SerializationBinder> para cambiar la versión de un tipo genérico cuando se serializa.  
  
## <a name="demonstrates"></a>Demostraciones  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra cómo dos entidades que están destinadas a versiones diferentes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] pueden comunicar utilizando el formateador binario y el enlazador de serialización.  
  
 El desarrollo de este ejemplo se ha realizado con .NET Remoting. El ejemplo está compuesto de un servidor para [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], que implementa un contrato con tipos genéricos, y dos clientes diferentes, uno para [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] y otro para [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].  
  
 El servidor asocia un objeto <xref:System.Runtime.Serialization.SerializationBinder> al formateador binario para poder cambiar la versión de los tipos de acuerdo con la serialización, de modo que ambos clientes puedan deserializar esos tipos correctamente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo  
  
1.  Para ejecutar el cliente, haga clic en la solución, SBGenericsVTS (6 proyectos) y, a continuación, seleccione **propiedades**.  
  
2.  En **propiedades comunes**, seleccione **proyecto de inicio**, a continuación, seleccione **proyectos de inicio múltiples**.  
  
3.  Seleccione **Server** primero, a continuación, **Client20** y, a continuación, **Client40**. Seleccione el **iniciar** acción para estos tres proyectos y deje el resto establecido en **ninguno**.  
  
4.  Haga clic en **Aceptar** y, a continuación, presione F5 para ejecutar el ejemplo.
