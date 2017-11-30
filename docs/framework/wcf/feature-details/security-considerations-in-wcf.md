---
title: Consideraciones de seguridad en WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
caps.latest.revision: "49"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c0af5a5d96f20b2ba5118909a3f0c5ba405bdb11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="security-considerations-in-wcf"></a>Consideraciones de seguridad en WCF
Los temas en esta sección enumeran varios elementos relacionados con la seguridad a considerar al diseñar una aplicación de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
 [Divulgación de información](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 Discute las varias maneras en las que se puede divulgar información o en las que se puede atacar a la información y cómo mitigarlo.  
  
 [Elevación de privilegios](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 Discute los efectos de proporcionar permisos de autorización a un atacante más allá de aquéllos concedidos inicialmente y cómo mitigarlo.  
  
 [Denegación de servicio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 Discute lo que pasa cuando un sistema no puede procesar apropiadamente los mensajes y cómo mitigarlo.  
  
 [Manipulación](../../../../docs/framework/wcf/feature-details/tampering.md)  
 Discute la modificación de mensajes o de la entrega de mensajes y cómo mitigarlo.  
  
 [Ataques de reproducción](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 Discute lo que pasa cuando un atacante copia una secuencia de mensajes entre dos usuarios y vuelve a reproducir la secuencia para uno o más de los usuarios, y cómo mitigar esto.  
  
 [Consideraciones de seguridad para las sesiones seguras](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 Discute los siguientes elementos que afectan a la seguridad al implementar sesiones seguras.  
  
 [Escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 Hace una lista de varios escenarios que no admiten ningún aspecto determinado de seguridad y que se deberían evitar o tener en cuenta.  
  
## <a name="reference"></a>Referencia  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Guía de seguridad y procedimientos recomendados](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>Vea también  
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)
