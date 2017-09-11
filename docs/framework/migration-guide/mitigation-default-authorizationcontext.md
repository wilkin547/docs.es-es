---
title: "Mitigación: AuthorizationContext predeterminado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 48363d0f8e515b703e49761a763379566e217844
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-default-authorizationcontext"></a><span data-ttu-id="d612c-102">Mitigación: AuthorizationContext predeterminado</span><span class="sxs-lookup"><span data-stu-id="d612c-102">Mitigation: Default AuthorizationContext</span></span>
<span data-ttu-id="d612c-103">La implementación de <xref:System.IdentityModel.Policy.AuthorizationContext> devuelto por una llamada a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> con un argumento `null``authorizationPolicies` ha cambiado su implementación en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d612c-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> with a `null``authorizationPolicies` argument has changed its implementation in the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d612c-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="d612c-104">Impact</span></span>  
 <span data-ttu-id="d612c-105">En raras ocasiones, las aplicaciones WCF que usan la autenticación personalizada pueden sufrir diferencias de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d612c-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d612c-106">Mitigación</span><span class="sxs-lookup"><span data-stu-id="d612c-106">Mitigation</span></span>  
 <span data-ttu-id="d612c-107">Puede restaurar el comportamiento anterior de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="d612c-107">You can restore the previous behavior in either of two ways:</span></span>  
  
-   <span data-ttu-id="d612c-108">Vuelva a compilar la aplicación para que se dirija a una versión anterior a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="d612c-108">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="d612c-109">Para los servicios hospedados en IIS, use el elemento `<httpRuntime targetFramework="x.x" />` para que se dirija a una versión anterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d612c-109">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x" />` element to target an earlier version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="d612c-110">Agregue la siguiente línea a la sección `<appSettings>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="d612c-110">Add the following line to the `<appSettings>` section of your app.config file:</span></span>  
  
    ```xml  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d612c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d612c-111">See Also</span></span>  
 [<span data-ttu-id="d612c-112">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="d612c-112">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

