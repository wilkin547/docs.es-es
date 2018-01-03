---
title: Eventos ETW en Common Language Runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ad262c2c813b5baa9dbde475e40cd445bd06701
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="etw-events-in-the-common-language-runtime"></a>Eventos ETW en Common Language Runtime
Common Language Runtime (CLR) proporciona información de diagnóstico del Seguimiento de eventos para Windows (ETW) útil para una gran variedad de eventos de depuración y de generación de perfiles. Los eventos ETW de CLR se aprovechan del sistema de seguimiento ETW de Windows para aumentar la compatibilidad con la depuración y generación de perfiles proporcionada por Common Language Runtime.  
  
 Puede encontrar más información sobre ETW disponible en el artículo [Improve Debugging and Performance Tuning with ETW](http://go.microsoft.com/fwlink/?LinkID=161142) (Mejorar la depuración y el ajuste de rendimiento con ETW) en MSDN. La información sobre Xperf se puede encontrar en la entrada [Kit de herramientas de rendimiento de Windows - Xperf](http://go.microsoft.com/fwlink/?LinkID=161144) del blog de NTDebugging.  
  
 Se requiere [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] o posterior para todos los eventos descritos en los temas de eventos. El sistema operativo Windows Vista es el cliente compatible mínimo, y Windows Server 2008 es el servidor compatible mínimo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Controlar el registro de .NET Framework](../../../docs/framework/performance/controlling-logging.md)  
 Describe las herramientas y los comandos para capturar y ver los eventos ETW.  
  
 [Proveedores ETW de CLR](../../../docs/framework/performance/clr-etw-providers.md)  
 Proporciona información sobre los proveedores de runtime y de detención; además, explica el modo de usarlos para la recopilación de datos ETW.  
  
 [Palabras clave y niveles ETW de CLR](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 Describe las palabras clave para los proveedores de runtime y de detención que habilitan el filtrado de eventos por categoría.  
  
 [CLR ETW Events (Eventos ETW de CLR)](../../../docs/framework/performance/clr-etw-events.md)  
 Proporciona información detallada sobre eventos ETW de CLR, sus palabras clave, niveles y datos de evento.  
  
## <a name="see-also"></a>Vea también  
 [Eventos ETW en .NET Framework](../../../docs/framework/performance/etw-events.md)
