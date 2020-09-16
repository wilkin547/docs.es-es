---
title: Autorización en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: c86a07b96b15963af9f078b52bc0d28e9a38187a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556263"
---
# <a name="authorization-in-wcf"></a>Autorización en WCF
La autorización es el proceso para controlar el acceso y los derechos a los recursos, como servicios o archivos. En los temas de esta sección se muestra cómo realizar esta tarea básica en Windows Communication Foundation (WCF) de varias maneras.  
  
## <a name="in-this-section"></a>En esta sección  
 [Mecanismos de control de acceso](access-control-mechanisms.md)  
 Proporciona una breve descripción de los mecanismos de autorización en WCF y los usos sugeridos.  
  
 [Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Muestra el proceso de restringir el acceso a un servicio con <xref:System.Security.Permissions.PrincipalPermissionAttribute>.  
  
 [Procedimiento para usar el proveedor de roles ASP.NET con un servicio](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Le guía a través de la configuración de un servicio para que pueda usar la característica de proveedor de roles de ASP.NET.  
  
 [Procedimiento para usar el proveedor de roles del administrador de autorización de ASP.NET con un servicio](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 ASP.NET puede usar el administrador de autorización para administrar la autorización de un sitio Web. WCF puede aprovechar de forma similar la combinación de ASP.NET/Authorization Manager para la autorización de clientes.  
  
 [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md)  
 Explica los fundamentos para utilizar la infraestructura del modelo de identidad para la autorización basada en demandas.  
  
 [Delegación y suplantación](delegation-and-impersonation-with-wcf.md)  
 Explica la diferencia entre la delegación y la suplantación.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Autenticación](authentication-in-wcf.md)  
  
## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](security-overview.md)
- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
