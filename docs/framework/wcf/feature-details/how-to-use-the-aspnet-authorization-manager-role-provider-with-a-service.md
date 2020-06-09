---
title: Procedimiento para usar el proveedor de roles del administrador de autorización de ASP.NET con un servicio
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 7c1076671512b33f115950cad684fba0b514abe9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595341"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="2d329-102">Procedimiento para usar el proveedor de roles del administrador de autorización de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="2d329-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="2d329-103">Cuando ASP.NET hospeda un servicio Web, puede integrar el administrador de autorización en la aplicación para proporcionar autorización para el servicio.</span><span class="sxs-lookup"><span data-stu-id="2d329-103">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="2d329-104">El administrador de autorización permite a los desarrolladores de aplicaciones definir operaciones individuales que, a su vez, pueden agruparse para formar tareas.</span><span class="sxs-lookup"><span data-stu-id="2d329-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="2d329-105">Un administrador puede autorizar funciones que realicen tareas específicas u operaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="2d329-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="2d329-106">El administrador de autorización proporciona una herramienta de administración, como complemento de Microsoft Management Console (MMC), para administrar funciones, tareas, operaciones y usuarios.</span><span class="sxs-lookup"><span data-stu-id="2d329-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="2d329-107">Los administradores configuran un almacén de directivas del administrador de autorización en un archivo XML, en Active Directory, o en un almacén de Active Directory Application Mode (ADAM).</span><span class="sxs-lookup"><span data-stu-id="2d329-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="2d329-108">El administrador de autorización se integra en la aplicación mediante la configuración del proveedor de funciones ASP.NET de administrador de autorización para la aplicación ASP.NET que hospeda el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="2d329-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="2d329-109">Al igual que otros proveedores de roles de ASP.NET, el proveedor de roles ASP.NET de administrador de autorización se configura mediante el `providers` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="2d329-109">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="2d329-110">El siguiente ejemplo de código forma parte del archivo de configuración de un servicio web que integra el administrador de autorización en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d329-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
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
  
 <span data-ttu-id="2d329-111">Para obtener más información sobre la integración de un proveedor de roles de ASP.NET con una aplicación WCF, consulte [Cómo: usar el proveedor de roles ASP.net con un servicio](how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="2d329-111">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="2d329-112">Para obtener más información acerca del uso del administrador de autorización con ASP.NET, consulte [Cómo: usar el administrador de autorización (AzMan) con ASP.NET 2,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="2d329-112">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d329-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d329-113">See also</span></span>

- [<span data-ttu-id="2d329-114">Procedimiento para usar el proveedor de roles ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="2d329-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)
