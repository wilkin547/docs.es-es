---
title: "Migración de aplicaciones de .NET Remoting a WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7d305adf1810832016cdafbb60fc025f17e0786
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migración de aplicaciones de .NET Remoting a WCF
**Este tema es específico de una tecnología heredada que se mantiene para la compatibilidad con versiones anteriores con aplicaciones existentes y no se recomienda para nuevo desarrollo. Las aplicaciones distribuidas se deberían desarrollar usando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**  
  
 Hay dos maneras de sacar provecho de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con aplicaciones .NET Remoting existentes: la integración y la migración. La integración le permite tener .Net Remoting 2.0 e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ejecutándose lado a lado, permitiéndole exponer los mismos objetos de negocio sobre ambas tecnologías de manera simultánea sin tener que modificar su código existente de .NET Remoting 2.0. La integración requiere que trabaje con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o posterior. Si desea aprovecharse de las características de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y no necesita la compatibilidad de la conexión con sistemas de comunicación remota 2.0, puede migrar su servicio a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. La migración de .NET Remoting 2.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere la realización de cambios en la interfaz del objeto remoto y su configuración. En estos temas se explican en [de comunicación remota de Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Vea también  
 [Información conceptual](../../../../docs/framework/wcf/conceptual-overview.md)
