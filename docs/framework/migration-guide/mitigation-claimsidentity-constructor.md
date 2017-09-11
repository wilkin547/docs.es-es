---
title: "Mitigación: constructor ClaimsIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 946903f1-0fbf-4f67-805b-1eb48352024d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a50cbd69aa1f2c72adc9fc4d10a070f5faa0cf54
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-claimsidentity-constructor"></a><span data-ttu-id="d3918-102">Mitigación: constructor ClaimsIdentity</span><span class="sxs-lookup"><span data-stu-id="d3918-102">Mitigation: ClaimsIdentity Constructor</span></span>
<span data-ttu-id="d3918-103">A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], hay un cambio en cómo el constructor <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> establece la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d3918-103">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], there is change in how the <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> constructor sets the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property.</span></span> <span data-ttu-id="d3918-104">Si el argumento <xref:System.Security.Principal.IIdentity> es un objeto <xref:System.Security.Claims.ClaimsIdentity> y la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> de ese objeto <xref:System.Security.Claims.ClaimsIdentity> no es `null`, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> se conecta mediante el método <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d3918-104">If the <xref:System.Security.Principal.IIdentity> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="d3918-105">En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> se asocia como una referencia existente.</span><span class="sxs-lookup"><span data-stu-id="d3918-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached as a  existing reference.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d3918-106">Impacto</span><span class="sxs-lookup"><span data-stu-id="d3918-106">Impact</span></span>  
 <span data-ttu-id="d3918-107">A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> del nuevo objeto <xref:System.Security.Claims.ClaimsIdentity> no es igual a la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> del argumento <xref:System.Security.Principal.IIdentity> del constructor.</span><span class="sxs-lookup"><span data-stu-id="d3918-107">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity> argument.</span></span> <span data-ttu-id="d3918-108">En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y en versiones anteriores, sí es igual.</span><span class="sxs-lookup"><span data-stu-id="d3918-108">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, it is equal.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d3918-109">Mitigación</span><span class="sxs-lookup"><span data-stu-id="d3918-109">Mitigation</span></span>  
 <span data-ttu-id="d3918-110">Si no desea este comportamiento, puede restaurar el comportamiento anterior si establece el modificador `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` en el archivo de configuración de la aplicación en `true`.</span><span class="sxs-lookup"><span data-stu-id="d3918-110">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="d3918-111">Para ello, es necesario que agregue lo siguiente a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo web.config:</span><span class="sxs-lookup"><span data-stu-id="d3918-111">This requires that you add the following to  the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your web.config file:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3918-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3918-112">See Also</span></span>  
 [<span data-ttu-id="d3918-113">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="d3918-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

