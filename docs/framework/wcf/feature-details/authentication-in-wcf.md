---
title: Autenticación en WCF
description: Obtenga información sobre varios mecanismos de WCF que proporcionan autenticación, como la autenticación de Windows, los certificados X. 509 y el nombre de usuario y contraseña.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 4c3348cfb84b8571dc1f24b774ffcd691aaa5001
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247525"
---
# <a name="authentication-in-wcf"></a>Autenticación en WCF
En los temas siguientes se muestran una serie de mecanismos diferentes en Windows Communication Foundation (WCF) que proporcionan autenticación, por ejemplo, la autenticación de Windows, los certificados X. 509 y el nombre de usuario y contraseñas.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimiento para usar el proveedor de pertenencia de ASP.NET](how-to-use-the-aspnet-membership-provider.md)  
 Las características de ASP.NET incluyen una pertenencia y proveedor de funciones, una base de datos para almacenar pares de nombre de usuario/contraseña para la autenticación y funciones de usuario para la autorización. En este tema se explica cómo los servicios WCF pueden usar la misma base de datos para autenticar y autorizar a los usuarios.  
  
 [Procedimiento para usar un nombre de usuario personalizado y un validador de contraseñas](how-to-use-a-custom-user-name-and-password-validator.md)  
 Muestra cómo integrar un validador de nombre de usuario/contraseña personalizado.  
  
 [Identidad del servicio y autenticación](service-identity-and-authentication.md)  
 Como medida de seguridad adicional, un cliente puede autenticar el servicio especificando la *identidad* esperada del servicio. Si la identidad esperada y la identidad devuelta por el servicio no coinciden, se produce un error de autenticación.  
  
 [Negociación de seguridad y tiempos de espera](security-negotiation-and-timeouts.md)  
 Describe cómo se utiliza la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> en la clase <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.  
  
 [Depuración de errores de autenticación de Windows](debugging-windows-authentication-errors.md)  
 Se centra en los problemas comunes que se producen cuando se usa la autenticación de Windows.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Escenarios de seguridad comunes](common-security-scenarios.md)  
  
## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](security-overview.md)
- [Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
