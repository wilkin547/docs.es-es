---
title: Migración de aplicaciones de .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 3f5556eeaf56ac48dd4f1d578ed2e66b90415677
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422950"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migración de aplicaciones de .NET Remoting a WCF
**Este tema es específico de una tecnología heredada que se mantiene para la compatibilidad con versiones anteriores con aplicaciones existentes y no se recomienda para nuevo desarrollo. Las aplicaciones distribuidas se deberían desarrollar con WCF.**  
  
 Hay dos maneras de sacar partido de WCF con las aplicaciones de .NET Remoting existentes: integración y migración. Integración le permite tener .net Remoting 2.0 y ejecución de WCF paralelo, lo que le permite exponer los mismos objetos de negocio sobre ambas tecnologías al mismo tiempo sin tener que modificar el existente de .net Remoting 2.0 código. La integración requiere que trabaje con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o posterior. Si desea aprovechar las características WCF y no necesita compatibilidad de conexión con sistemas de comunicación remota 2.0, puede migrar su servicio WCF. Migración de la versión 2.0 de .NET Remoting a WCF requiere cambios en la interfaz del objeto remoto y su configuración. Ambos de estos temas se tratan en [de Remoting a Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Vea también  
 [Información conceptual](../../../../docs/framework/wcf/conceptual-overview.md)
