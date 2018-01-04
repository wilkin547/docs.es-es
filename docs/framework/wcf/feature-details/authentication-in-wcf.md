---
title: "Autenticación en WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 432ed9debeffad82125b567508ed46b46d4b8821
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="authentication-in-wcf"></a>Autenticación en WCF
Los temas siguientes muestran varios mecanismos diferentes en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que proporciona autenticación, por ejemplo, autenticación de Windows, certificados X.509 y nombre de usuario y contraseñas.  
  
## <a name="in-this-section"></a>En esta sección  
 [Uso del proveedor de pertenencia de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 Las características de ASP.NET incluyen una pertenencia y proveedor de funciones, una base de datos para almacenar pares de nombre de usuario/contraseña para la autenticación y funciones de usuario para la autorización. En este tema se explica cómo los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden utilizar la misma base de datos para autenticar y autorizar a los usuarios.  
  
 [Uso de un nombre de usuario personalizado y un validador de contraseñas](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 Muestra cómo integrar un validador de nombre de usuario/contraseña personalizado.  
  
 [Identidad del servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 Como una medida de seguridad adicional, un cliente puede autenticar el servicio especificando el esperado *identidad* del servicio. Si la identidad esperada y la identidad devuelta por el servicio no coinciden, se produce un error de autenticación.  
  
 [Negociación de seguridad y tiempos de espera](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 Describe cómo se utiliza la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> en la clase <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.  
  
 [Depuración de errores de autenticación de Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 Se centra en los problemas comunes que se producen cuando se usa la autenticación de Windows.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Escenarios de seguridad comunes](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
