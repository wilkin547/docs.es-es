---
title: Migración de aplicaciones de .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: c0ce7c9badc8bad6eedc58827b6efe2595ab2cf8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592869"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migración de aplicaciones de .NET Remoting a WCF
**Este tema es específico de una tecnología heredada que se mantiene para la compatibilidad con versiones anteriores con aplicaciones existentes y no se recomienda para nuevo desarrollo. Las aplicaciones distribuidas se deberían desarrollar con WCF.**  
  
 Hay dos maneras de sacar partido de WCF con las aplicaciones de .NET Remoting existentes: integración y migración. Integración le permite tener .NET Remoting 2.0 y WCF está ejecutando en paralelo, lo que le permite exponer los mismos objetos de negocio sobre ambas tecnologías al mismo tiempo sin tener que modificar el código de .NET Remoting 2.0 existente. Integración requiere que se está ejecutando en .NET Framework 2.0 o posterior. Si desea aprovechar las características WCF y no necesita compatibilidad de conexión con sistemas de comunicación remota 2.0, puede migrar su servicio WCF. Migración de la versión 2.0 de .NET Remoting a WCF requiere cambios en la interfaz del objeto remoto y su configuración. Ambos de estos temas se tratan en [de Remoting a Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Vea también

- [Información conceptual](../../../../docs/framework/wcf/conceptual-overview.md)
