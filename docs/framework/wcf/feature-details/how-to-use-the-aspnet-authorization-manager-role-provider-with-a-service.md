---
title: Cómo utilizar el proveedor de funciones del administrador de autorización de ASP.NET con un servicio
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 009b96defdf27591ddb98afaa684745b5fcbe0d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184808"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Cómo utilizar el proveedor de funciones del administrador de autorización de ASP.NET con un servicio
Al ASP.NET hospeda un servicio web, puede integrar El Administrador de autorización en la aplicación para proporcionar autorización al servicio. El administrador de autorización permite a los desarrolladores de aplicaciones definir operaciones individuales que, a su vez, pueden agruparse para formar tareas. Un administrador puede autorizar funciones que realicen tareas específicas u operaciones individuales. El administrador de autorización proporciona una herramienta de administración, como complemento de Microsoft Management Console (MMC), para administrar funciones, tareas, operaciones y usuarios. Los administradores configuran un almacén de directivas del administrador de autorización en un archivo XML, en Active Directory, o en un almacén de Active Directory Application Mode (ADAM).  
  
 El Administrador de autorización se integra en la aplicación configurando el Administrador de autorización ASP.NET proveedor de roles para la aplicación ASP.NET que hospeda el servicio web. Al igual que otros proveedores de roles ASP.NET, `providers` el proveedor de roles de ASP.NET del Administrador de autorización se configura mediante el elemento <>.  
  
 El siguiente ejemplo de código forma parte del archivo de configuración de un servicio web que integra el administrador de autorización en la aplicación.  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 Para obtener más información acerca de cómo integrar un proveedor de roles de ASP.NET con una aplicación WCF, vea [Cómo: usar el ASP.NET proveedor](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)de roles con un servicio . Para obtener más información sobre el uso de Authorization Manager con ASP.NET, consulte Cómo: Usar el Administrador de [autorización (AzMan) con ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).  
  
## <a name="see-also"></a>Consulte también

- [Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
