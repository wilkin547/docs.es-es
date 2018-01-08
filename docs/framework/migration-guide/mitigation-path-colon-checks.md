---
title: "Mitigación: comprobaciones de dos puntos en las rutas de acceso"
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
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a976e4491924f91e97f01a9b98db945699655196
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="ec6fc-102">Mitigación: comprobaciones de dos puntos en las rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="ec6fc-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="ec6fc-103">A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], se han realizado una serie de cambios para admitir rutas de acceso que anteriormente no eran compatibles (en términos de longitud y formato).</span><span class="sxs-lookup"><span data-stu-id="ec6fc-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="ec6fc-104">En concreto, las comprobaciones de la sintaxis de separador de la unidad correspondiente (dos puntos) se realizan de manera más correcta.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ec6fc-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="ec6fc-105">Impact</span></span>  
 <span data-ttu-id="ec6fc-106">Estos cambios bloquean algunas rutas del identificador URI que los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> admitían anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ec6fc-107">Mitigación</span><span class="sxs-lookup"><span data-stu-id="ec6fc-107">Mitigation</span></span>  
 <span data-ttu-id="ec6fc-108">Para solucionar el problema de una ruta de acceso anteriormente aceptable que ya no es compatible con los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, puede llevar a cabo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec6fc-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
-   <span data-ttu-id="ec6fc-109">Quitar manualmente el esquema de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="ec6fc-110">Por ejemplo, quitar `file://` de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-110">For example, remove `file://` from a URL.</span></span>  
  
-   <span data-ttu-id="ec6fc-111">Pasar el identificador URI al constructor <xref:System.Uri> y recuperar el valor de la propiedad <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
-   <span data-ttu-id="ec6fc-112">Rechazar la nueva normalización de la ruta de acceso mediante el establecimiento del conmutador `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> en `true`.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ec6fc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec6fc-113">See Also</span></span>  
 [<span data-ttu-id="ec6fc-114">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="ec6fc-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
