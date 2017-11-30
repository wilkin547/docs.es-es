---
title: Seguridad de comportamiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9182c95b9770cac94b2a747e277fcd0cc02b387f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="behavior-security"></a>Seguridad de comportamiento
En esta sección se incluyen ejemplos que muestran cómo configurar la seguridad para los comportamientos del servicio.  
  
## <a name="in-this-section"></a>En esta sección  
 [Comportamiento de auditoría de servicio](../../../../docs/framework/wcf/samples/service-auditing-behavior.md)  
 Este ejemplo muestra cómo utilizar <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> para habilitar la auditoría de eventos de seguridad durante las operaciones de servicio.  
  
 [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 Este ejemplo muestra el modo en que un servicio puede utilizar los proveedores de pertenencia y roles de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] para autenticar y autorizar a los clientes.  
  
 [Autorizar el acceso a las operaciones de servicio](../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 Este ejemplo muestra cómo utilizar el [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) para habilitar el uso de la <xref:System.Security.Permissions.PrincipalPermissionAttribute> atributo para autorizar el acceso a las operaciones de servicio.  
  
 [Suplanta al cliente](../../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 Este ejemplo muestra cómo suplantar la aplicación del autor de la llamada en el servicio para que el servicio pueda tener acceso a los recursos del sistema en nombre del autor de la llamada.
