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
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="fb114-102">Cómo utilizar el proveedor de funciones del administrador de autorización de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="fb114-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="fb114-103">Al ASP.NET hospeda un servicio web, puede integrar El Administrador de autorización en la aplicación para proporcionar autorización al servicio.</span><span class="sxs-lookup"><span data-stu-id="fb114-103">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="fb114-104">El administrador de autorización permite a los desarrolladores de aplicaciones definir operaciones individuales que, a su vez, pueden agruparse para formar tareas.</span><span class="sxs-lookup"><span data-stu-id="fb114-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="fb114-105">Un administrador puede autorizar funciones que realicen tareas específicas u operaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="fb114-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="fb114-106">El administrador de autorización proporciona una herramienta de administración, como complemento de Microsoft Management Console (MMC), para administrar funciones, tareas, operaciones y usuarios.</span><span class="sxs-lookup"><span data-stu-id="fb114-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="fb114-107">Los administradores configuran un almacén de directivas del administrador de autorización en un archivo XML, en Active Directory, o en un almacén de Active Directory Application Mode (ADAM).</span><span class="sxs-lookup"><span data-stu-id="fb114-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="fb114-108">El Administrador de autorización se integra en la aplicación configurando el Administrador de autorización ASP.NET proveedor de roles para la aplicación ASP.NET que hospeda el servicio web.</span><span class="sxs-lookup"><span data-stu-id="fb114-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="fb114-109">Al igual que otros proveedores de roles ASP.NET, `providers` el proveedor de roles de ASP.NET del Administrador de autorización se configura mediante el elemento <>.</span><span class="sxs-lookup"><span data-stu-id="fb114-109">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="fb114-110">El siguiente ejemplo de código forma parte del archivo de configuración de un servicio web que integra el administrador de autorización en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fb114-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
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
  
 <span data-ttu-id="fb114-111">Para obtener más información acerca de cómo integrar un proveedor de roles de ASP.NET con una aplicación WCF, vea [Cómo: usar el ASP.NET proveedor](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)de roles con un servicio .</span><span class="sxs-lookup"><span data-stu-id="fb114-111">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="fb114-112">Para obtener más información sobre el uso de Authorization Manager con ASP.NET, consulte Cómo: Usar el Administrador de [autorización (AzMan) con ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="fb114-112">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb114-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb114-113">See also</span></span>

- [<span data-ttu-id="fb114-114">Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="fb114-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
