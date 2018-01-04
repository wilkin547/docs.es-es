---
title: "Autorización en WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac43b2185048287d0edd4cb20561a936bce2f58b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="authorization-in-wcf"></a>Autorización en WCF
La autorización es el proceso para controlar el acceso y los derechos a los recursos, como servicios o archivos. Los temas en esta presentación de la sección le muestran cómo realizar esta tarea básica en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en una gran variedad de maneras.  
  
## <a name="in-this-section"></a>En esta sección  
 [Mecanismos de control de acceso](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 Proporciona un esquema breve de los mecanismos de la autorización en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]y los usos sugeridos.  
  
 [Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Muestra el proceso de restringir el acceso a un servicio con <xref:System.Security.Permissions.PrincipalPermissionAttribute>.  
  
 [Uso del proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Abarca la configuración de un servicio para permitirle utilizar la característica de proveedor de funciones de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
 [Uso del proveedor de funciones del administrador de autorización de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] puede usar el Administrador de autorización para administrar la autorización para un sitio web. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede aprovechar igualmente la combinación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Administrador de autorización para la autorización de clientes.  
  
 [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 Explica los fundamentos para utilizar la infraestructura del modelo de identidad para la autorización basada en demandas.  
  
 [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 Explica la diferencia entre la delegación y la suplantación.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Autenticación](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
