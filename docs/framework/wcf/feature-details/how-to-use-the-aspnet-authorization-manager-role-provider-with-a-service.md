---
title: Cómo utilizar el proveedor de funciones del administrador de autorización de ASP.NET con un servicio
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: c21c1a80468bd81f2df69009afd2be86ee714250
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516713"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="3b014-102">Cómo utilizar el proveedor de funciones del administrador de autorización de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="3b014-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="3b014-103">Cuando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospeda un servicio web, se puede integrar el administrador de autorización en la aplicación para autorizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="3b014-103">When [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="3b014-104">El administrador de autorización permite a los desarrolladores de aplicaciones definir operaciones individuales que, a su vez, pueden agruparse para formar tareas.</span><span class="sxs-lookup"><span data-stu-id="3b014-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="3b014-105">Un administrador puede autorizar funciones que realicen tareas específicas u operaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="3b014-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="3b014-106">El administrador de autorización proporciona una herramienta de administración, como complemento de Microsoft Management Console (MMC), para administrar funciones, tareas, operaciones y usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b014-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="3b014-107">Los administradores configuran un almacén de directivas del administrador de autorización en un archivo XML, en Active Directory, o en un almacén de Active Directory Application Mode (ADAM).</span><span class="sxs-lookup"><span data-stu-id="3b014-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="3b014-108">El administrador de autorización se integra en la aplicación mediante la configuración del [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de funciones del administrador de autorización de la aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que hospeda el servicio web.</span><span class="sxs-lookup"><span data-stu-id="3b014-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider for the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is hosting the Web service.</span></span> <span data-ttu-id="3b014-109">Al igual que otros proveedores de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], el proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del administrador de autorización se configura mediante el elemento <`providers`>.</span><span class="sxs-lookup"><span data-stu-id="3b014-109">Like other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role providers, the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="3b014-110">El siguiente ejemplo de código forma parte del archivo de configuración de un servicio web que integra el administrador de autorización en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3b014-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
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
  
 <span data-ttu-id="3b014-111">Para obtener más información acerca de cómo integrar un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de roles con una aplicación de WCF, vea [Cómo: utilizar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="3b014-111">For more information about integrating an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="3b014-112">Para obtener más información sobre cómo usar el Administrador de autorización con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], consulte [Cómo: usar el Administrador de autorización (AzMan) con ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span><span class="sxs-lookup"><span data-stu-id="3b014-112">For more information about using Authorization Manager with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b014-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b014-113">See Also</span></span>  
 [<span data-ttu-id="3b014-114">Uso del proveedor de funciones ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="3b014-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
