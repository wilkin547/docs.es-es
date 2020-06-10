---
title: Sesiones seguras
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: cb02adc7514e27175088e7664b12e45bc8ca5cd9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590090"
---
# <a name="secure-sessions"></a>Sesiones seguras
Una característica de Windows Communication Foundation (WCF) son las sesiones confiables que garantizan que los mensajes se reciben en el orden en que se enviaron. Los temas de esta sección discuten las implicaciones de seguridad a tener en cuenta a la hora de crear una sesión confiable. Para obtener más información acerca de las sesiones confiables, vea [uso de sesiones](../using-sessions.md).  
  
> [!NOTE]
> Si se requiere la suplantación en Windows XP, utilice una sesión segura sin un token de contexto de seguridad con estado (SCT). Cuando se utilizan SCT con estado con suplantación, se produce una <xref:System.InvalidOperationException>. Para obtener más información, vea [escenarios no admitidos](unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
|||  
|-|-|  
|[Conversaciones y sesiones seguras](secure-conversations-and-secure-sessions.md)|Las conversaciones seguras y las sesiones seguras hacen referencia al mismo concepto. En este tema se explica la manera en la que funciona una conversación segura, así como cuándo y por qué utilizar el patrón.|  
|[Procedimiento para crear una sesión segura](how-to-create-a-secure-session.md)|Tutorial sobre los fundamentos de la creación de sesiones seguras.|  
|[Procedimiento para crear un token de contexto de seguridad para una sesión segura](how-to-create-a-security-context-token-for-a-secure-session.md)|Describe los pasos necesarios para la creación de una batería de servidores web que mantendrán estado y sesiones con clientes.|  
|[Consideraciones de seguridad para sesiones seguras](security-considerations-for-secure-sessions.md)|Describe consideraciones especiales de las sesiones seguras.|  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Sesiones, creación de instancias y simultaneidad](sessions-instancing-and-concurrency.md)  
  
 [Diseño e implementación de servicios](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para habilitar la detección de repetición de mensajes](how-to-enable-message-replay-detection.md)
- [Ataques por repetición](replay-attacks.md)
- [Procedimiento para crear un servicio que requiere sesiones](how-to-create-a-service-that-requires-sessions.md)
