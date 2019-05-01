---
title: Procedimiento para usar el proveedor de roles del administrador de autorización de ASP.NET con un servicio
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: ebdfa8bd7d222c4f9a33b6718b215d327d589c6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047300"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Procedimiento para usar el proveedor de roles del administrador de autorización de ASP.NET con un servicio
Cuando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospeda un servicio web, se puede integrar el administrador de autorización en la aplicación para autorizar el servicio. El administrador de autorización permite a los desarrolladores de aplicaciones definir operaciones individuales que, a su vez, pueden agruparse para formar tareas. Un administrador puede autorizar funciones que realicen tareas específicas u operaciones individuales. El administrador de autorización proporciona una herramienta de administración, como complemento de Microsoft Management Console (MMC), para administrar funciones, tareas, operaciones y usuarios. Los administradores configuran un almacén de directivas del administrador de autorización en un archivo XML, en Active Directory, o en un almacén de Active Directory Application Mode (ADAM).  
  
 El administrador de autorización se integra en la aplicación mediante la configuración del [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de funciones del administrador de autorización de la aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que hospeda el servicio web. Al igual que otros [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedores de roles, el Administrador de autorización [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de roles se configura mediante el <`providers`> elemento.  
  
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
  
 Para obtener más información acerca de cómo integrar un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de roles con una aplicación de WCF, vea [Cómo: Usar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md). Para obtener más información sobre cómo usar el Administrador de autorización con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], vea [Cómo: Usar el Administrador de autorización (AzMan) con ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).  
  
## <a name="see-also"></a>Vea también

- [Cómo: Usar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
