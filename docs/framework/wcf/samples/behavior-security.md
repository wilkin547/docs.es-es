---
title: Seguridad de comportamiento
ms.date: 03/30/2017
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
ms.openlocfilehash: 5d09fcc2068133b3bb302850a647a2539ab07ee3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575594"
---
# <a name="behavior-security"></a>Seguridad de comportamiento
En esta sección se incluyen ejemplos que muestran cómo configurar la seguridad para los comportamientos del servicio.  
  
## <a name="in-this-section"></a>En esta sección  
 [Comportamiento de auditoría de servicio](service-auditing-behavior.md)  
 Este ejemplo muestra cómo utilizar <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> para habilitar la auditoría de eventos de seguridad durante las operaciones de servicio.  
  
 [Proveedor de pertenencia y roles](membership-and-role-provider.md)  
 Este ejemplo muestra cómo un servicio puede usar la pertenencia a ASP.NET y los proveedores de roles para autenticar y autorizar a los clientes.  
  
 [Autorización de acceso a operaciones de servicio](authorizing-access-to-service-operations.md)  
 Este ejemplo muestra cómo utilizar [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) para habilitar el uso del <xref:System.Security.Permissions.PrincipalPermissionAttribute> atributo para autorizar el acceso a las operaciones de servicio.  
  
 [Suplantar el cliente](impersonating-the-client.md)  
 Este ejemplo muestra cómo suplantar la aplicación del autor de la llamada en el servicio para que el servicio pueda tener acceso a los recursos del sistema en nombre del autor de la llamada.
