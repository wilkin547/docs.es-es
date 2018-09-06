---
title: Autenticación en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 401bd8901f4d8b9292e83d3e54d0afce30c9584f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785835"
---
# <a name="authentication-in-wcf"></a>Autenticación en WCF
Los temas siguientes muestran varios mecanismos diferentes en Windows Communication Foundation (WCF) que proporciona autenticación, por ejemplo, autenticación de Windows, los certificados X.509 y nombre de usuario y contraseñas.  
  
## <a name="in-this-section"></a>En esta sección  
 [Uso del proveedor de pertenencia de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 Las características de ASP.NET incluyen una pertenencia y proveedor de funciones, una base de datos para almacenar pares de nombre de usuario/contraseña para la autenticación y funciones de usuario para la autorización. En este tema se explica cómo los servicios de WCF pueden usar la misma base de datos para autenticar y autorizar a los usuarios.  
  
 [Uso de un nombre de usuario personalizado y un validador de contraseñas](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 Muestra cómo integrar un validador de nombre de usuario/contraseña personalizado.  
  
 [Identidad del servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 Como una medida de seguridad adicional, un cliente puede autenticar el servicio mediante la especificación de la esperada *identidad* del servicio. Si la identidad esperada y la identidad devuelta por el servicio no coinciden, se produce un error de autenticación.  
  
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
 [Modelo de seguridad de Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
