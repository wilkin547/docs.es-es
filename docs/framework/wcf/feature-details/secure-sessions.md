---
title: Sesiones seguras
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: 63e363e90a656c918b68d3f86d8b6ad3b7a540e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715717"
---
# <a name="secure-sessions"></a>Sesiones seguras
Una característica de Windows Communication Foundation (WCF) es las sesiones fiables que garantizan que los mensajes se reciben en el orden en que fueron enviados. Los temas de esta sección discuten las implicaciones de seguridad a tener en cuenta a la hora de crear una sesión confiable. Para obtener más información acerca de las sesiones confiables, vea [mediante sesiones](../../../../docs/framework/wcf/using-sessions.md).  
  
> [!NOTE]
>  Si se requiere la suplantación en Windows XP, utilice una sesión segura sin un token de contexto de seguridad con estado (SCT). Cuando se utilizan SCT con estado con suplantación, se produce una <xref:System.InvalidOperationException>. Para obtener más información, consulte [escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
|||  
|-|-|  
|[Conversaciones y sesiones seguras](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|Las conversaciones seguras y las sesiones seguras hacen referencia al mismo concepto. En este tema se explica la manera en la que funciona una conversación segura, así como cuándo y por qué utilizar el patrón.|  
|[Cómo: Crear una sesión segura](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|Tutorial sobre los fundamentos de la creación de sesiones seguras.|  
|[Cómo: Crear un contexto de seguridad Token para una sesión segura](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|Describe los pasos necesarios para la creación de una batería de servidores web que mantendrán estado y sesiones con clientes.|  
|[Consideraciones de seguridad para sesiones seguras](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|Describe consideraciones especiales de las sesiones seguras.|  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [Diseño e implementación de servicios](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a>Vea también
- [Cómo: Habilitar la detección de reproducción de mensajes](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)
- [Ataques por repetición](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [Cómo: Crear un servicio que requiere sesiones](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
