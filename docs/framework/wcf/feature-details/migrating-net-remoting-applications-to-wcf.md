---
title: Migración de aplicaciones de .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 53f63352503a48ee849580e676b5fe98f3dcf2cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492501"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migración de aplicaciones de .NET Remoting a WCF
**Este tema es específico de una tecnología heredada que se mantiene para la compatibilidad con versiones anteriores con aplicaciones existentes y no se recomienda para nuevo desarrollo. Ahora se deben desarrollar aplicaciones distribuidas con WCF.**  
  
 Hay dos maneras de sacar partido de WCF con las aplicaciones de .NET Remoting existentes: integración y la migración. Integración le permite tener .net Remoting 2.0 y WCF que se ejecutan en paralelo en paralelo, lo que le permite exponer los mismos objetos de negocio sobre ambas tecnologías al mismo tiempo sin tener que modificar el existente de .net Remoting 2.0 código. La integración requiere que trabaje con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o posterior. Si desea aprovechar las características WCF y no necesita la compatibilidad de la conexión con sistemas de comunicación remota 2.0, puede migrar su servicio a WCF. Migración de la versión 2.0 de .NET Remoting a WCF requiere cambios en la interfaz del objeto remoto y su configuración. En estos temas se explican en [de comunicación remota de Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Vea también  
 [Información conceptual](../../../../docs/framework/wcf/conceptual-overview.md)
