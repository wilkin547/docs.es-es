---
title: "Mitigación: Compatibilidad con formato largo de ruta de acceso"
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
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 138e96c3d45b79ccf30f6a3d39f0af26a48c0117
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-long-path-support"></a><span data-ttu-id="62f7e-102">Mitigación: Compatibilidad con formato largo de ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="62f7e-102">Mitigation: Long Path Support</span></span>
<span data-ttu-id="62f7e-103">A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], los métodos de E/S del sistema de archivos ya no muestran automáticamente un elemento `MAX_PATH` si la ruta de acceso o el nombre de archivo completo supera los 260 (o <xref:System.IO.PathTooLongException>) caracteres.</span><span class="sxs-lookup"><span data-stu-id="62f7e-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)],  file system I/O methods not longer automatically throw a <xref:System.IO.PathTooLongException> if a path or fully qualified file name exceeds 260 (or `MAX_PATH`) characters.</span></span> <span data-ttu-id="62f7e-104">En su lugar, son compatibles las rutas de acceso con formato largo de hasta 32 000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="62f7e-104">Instead, long paths of up to 32K characters are supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="62f7e-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="62f7e-105">Impact</span></span>  
 <span data-ttu-id="62f7e-106">Las aplicaciones que se han vuelto a compilar para destinarlas a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] y que mostraban anteriormente <xref:System.IO.PathTooLongException> automáticamente porque la ruta de acceso superaba los 260 caracteres, ahora mostrarán <xref:System.IO.PathTooLongException> solo si se cumplen las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="62f7e-106">Apps recompiled to target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] and that previously threw a <xref:System.IO.PathTooLongException> automatically because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException> only under the following conditions:</span></span>  
  
-   <span data-ttu-id="62f7e-107">La longitud de la cadena debe ser mayor que <xref:System.Int16.MaxValue?displayProperty=fullName> (32767) caracteres.</span><span class="sxs-lookup"><span data-stu-id="62f7e-107">The length of the path is greater than  <xref:System.Int16.MaxValue?displayProperty=fullName> (32,767) characters.</span></span>  
  
-   <span data-ttu-id="62f7e-108">El sistema operativo devuelve `COR_E_PATHTOOLONG` o su equivalente.</span><span class="sxs-lookup"><span data-stu-id="62f7e-108">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>  
  
 <span data-ttu-id="62f7e-109">El comportamiento heredado para las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores es que el runtime muestra automáticamente un elemento <xref:System.IO.PathTooLongException> cada vez que una ruta de acceso supera los 260 caracteres.</span><span class="sxs-lookup"><span data-stu-id="62f7e-109">The legacy behavior for apps that target the[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier is that the runtime automatically throws a <xref:System.IO.PathTooLongException> whenever a path exceeds 260 characters.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="62f7e-110">Mitigación</span><span class="sxs-lookup"><span data-stu-id="62f7e-110">Mitigation</span></span>  
 <span data-ttu-id="62f7e-111">Para las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], puede rechazar la compatibilidad con el formato largo de ruta de acceso si no la desea agregando lo siguiente a la sección [ \<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="62f7e-111">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], you can opt out of long path support if it is not desirable by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 <span data-ttu-id="62f7e-112">Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versiones posteriores, puede incluir la compatibilidad con el formato largo de ruta de acceso agregando lo siguiente a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="62f7e-112">For apps that target earlier versions of the .NET Framework but run on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later., you can opt in to long path support by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62f7e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="62f7e-113">See Also</span></span>  
 [<span data-ttu-id="62f7e-114">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="62f7e-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

