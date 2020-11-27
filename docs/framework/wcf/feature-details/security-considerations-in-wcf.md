---
title: Consideraciones de seguridad en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: 796098258601ec5fa208fd8a8060b28c3eeeb4d6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276027"
---
# <a name="security-considerations-in-wcf"></a>Consideraciones de seguridad en WCF

En los temas de esta sección se enumeran varios elementos relacionados con la seguridad que se deben tener en cuenta al diseñar una aplicación Windows Communication Foundation (WCF).  
  
## <a name="in-this-section"></a>En esta sección  

 [Divulgación de información](information-disclosure.md)  
 Discute las varias maneras en las que se puede divulgar información o en las que se puede atacar a la información y cómo mitigarlo.  
  
 [Elevación de privilegios](elevation-of-privilege.md)  
 Discute los efectos de proporcionar permisos de autorización a un atacante más allá de aquéllos concedidos inicialmente y cómo mitigarlo.  
  
 [Denegación de servicio](denial-of-service.md)  
 Discute lo que pasa cuando un sistema no puede procesar apropiadamente los mensajes y cómo mitigarlo.  
  
 [Manipulación](tampering.md)  
 Discute la modificación de mensajes o de la entrega de mensajes y cómo mitigarlo.  
  
 [Ataques por repetición](replay-attacks.md)  
 Discute lo que pasa cuando un atacante copia una secuencia de mensajes entre dos usuarios y vuelve a reproducir la secuencia para uno o más de los usuarios, y cómo mitigar esto.  
  
 [Consideraciones de seguridad para sesiones seguras](security-considerations-for-secure-sessions.md)  
 Discute los siguientes elementos que afectan a la seguridad al implementar sesiones seguras.  
  
 [Escenarios no admitidos](unsupported-scenarios.md)  
 Hace una lista de varios escenarios que no admiten ningún aspecto determinado de seguridad y que se deberían evitar o tener en cuenta.  
  
## <a name="reference"></a>Referencia  

 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Orientación de seguridad y procedimientos recomendados](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>Vea también

- [Seguridad](security.md)
