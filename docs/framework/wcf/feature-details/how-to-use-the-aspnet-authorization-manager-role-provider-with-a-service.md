---
title: Cómo utilizar el proveedor de funciones del administrador de autorización de ASP.NET con un servicio
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 20955578ce4d344c2057036c0944557edf737389
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212221"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Cómo utilizar el proveedor de funciones del administrador de autorización de ASP.NET con un servicio
Cuando ASP.NET hospeda un servicio Web, puede integrar el administrador de autorización en la aplicación para proporcionar autorización para el servicio. El administrador de autorización permite a los desarrolladores de aplicaciones definir operaciones individuales que, a su vez, pueden agruparse para formar tareas. Un administrador puede autorizar funciones que realicen tareas específicas u operaciones individuales. El administrador de autorización proporciona una herramienta de administración, como complemento de Microsoft Management Console (MMC), para administrar funciones, tareas, operaciones y usuarios. Los administradores configuran un almacén de directivas del administrador de autorización en un archivo XML, en Active Directory, o en un almacén de Active Directory Application Mode (ADAM).  
  
 El administrador de autorización se integra en la aplicación mediante la configuración del proveedor de funciones ASP.NET de administrador de autorización para la aplicación ASP.NET que hospeda el servicio Web. Al igual que otros proveedores de roles de ASP.NET, el proveedor de roles de ASP.NET de administrador de autorización se configura mediante el < elemento de >`providers`.  
  
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
  
 Para obtener más información sobre la integración de un proveedor de roles de ASP.NET con una aplicación WCF, consulte [Cómo: usar el proveedor de roles ASP.net con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md). Para obtener más información acerca del uso del administrador de autorización con ASP.NET, consulte [Cómo: usar el administrador de autorización (AzMan) con ASP.NET 2,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).  
  
## <a name="see-also"></a>Vea también

- [Uso del proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
