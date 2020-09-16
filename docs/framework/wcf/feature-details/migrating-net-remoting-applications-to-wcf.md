---
title: Migración de aplicaciones de .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 6233c603c30dbd021050caa2c5fd9c1849c80700
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546515"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migración de aplicaciones de .NET Remoting a WCF
**Este tema es específico de una tecnología heredada que se conserva por compatibilidad con versiones anteriores de las aplicaciones existentes y no se recomienda para el nuevo desarrollo. Las aplicaciones distribuidas ahora deben desarrollarse mediante WCF.**  
  
 Hay dos maneras de aprovechar WCF con las aplicaciones de .NET Remoting existentes: integración y migración. La integración permite que .NET Remoting 2,0 y WCF se ejecuten en paralelo, lo que permite exponer los mismos objetos empresariales en ambas tecnologías simultáneamente sin tener que modificar el código existente de .NET Remoting 2,0. La integración requiere que se ejecute en .NET Framework 2,0 o superior. Si desea aprovechar las características de WCF y no necesita compatibilidad de conexión con sistemas de comunicación remota de 2,0, puede migrar todo el servicio a WCF. La migración de .NET Remoting 2,0 a WCF requiere cambios en la interfaz del objeto remoto y sus opciones de configuración. Ambos temas se tratan en [desde la comunicación remota con el Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).  
  
## <a name="see-also"></a>Vea también

- [Información general conceptual](../conceptual-overview.md)
