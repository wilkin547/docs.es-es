---
title: Autorización en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 26aa445f3136fcb16e2eb9cdce6b245476297dfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161379"
---
# <a name="authorization-in-wcf"></a>Autorización en WCF
La autorización es el proceso para controlar el acceso y los derechos a los recursos, como servicios o archivos. Los temas de esta sección muestran cómo realizar esta tarea básica en Windows Communication Foundation (WCF) en una variedad de formas.  
  
## <a name="in-this-section"></a>En esta sección  
 [Mecanismos de control de acceso](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 Proporciona una descripción breve de los mecanismos de autorización en WCF y usos sugeridos.  
  
 [Cómo: Restringir el acceso con la clase PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Muestra el proceso de restringir el acceso a un servicio con <xref:System.Security.Permissions.PrincipalPermissionAttribute>.  
  
 [Cómo: Usar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Abarca la configuración de un servicio para permitirle utilizar la característica de proveedor de funciones de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
 [Cómo: Usar el proveedor de roles de administrador de autorización de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] puede usar el Administrador de autorización para administrar la autorización para un sitio web. WCF de forma similar puede aprovechar el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]combinación /Authorization Manager para la autorización de clientes.  
  
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

- [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Modelo de seguridad de Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
