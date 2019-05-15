---
title: 'Mitigación: comprobaciones de dos puntos en las rutas de acceso'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6799e36ec312bf857a12293dc0be15e9cc21f55
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648452"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="4610b-102">Mitigación: comprobaciones de dos puntos en las rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="4610b-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="4610b-103">A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], se han realizado una serie de cambios para admitir rutas de acceso que anteriormente no eran compatibles (en términos de longitud y formato).</span><span class="sxs-lookup"><span data-stu-id="4610b-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="4610b-104">En concreto, las comprobaciones de la sintaxis de separador de la unidad correspondiente (dos puntos) se realizan de manera más correcta.</span><span class="sxs-lookup"><span data-stu-id="4610b-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="4610b-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="4610b-105">Impact</span></span>  
 <span data-ttu-id="4610b-106">Estos cambios bloquean algunas rutas del identificador URI que los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> admitían anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4610b-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="4610b-107">Mitigación</span><span class="sxs-lookup"><span data-stu-id="4610b-107">Mitigation</span></span>  
 <span data-ttu-id="4610b-108">Para solucionar el problema de una ruta de acceso anteriormente aceptable que ya no es compatible con los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, puede llevar a cabo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="4610b-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="4610b-109">Quitar manualmente el esquema de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="4610b-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="4610b-110">Por ejemplo, quitar `file://` de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="4610b-110">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="4610b-111">Pasar el identificador URI al constructor <xref:System.Uri> y recuperar el valor de la propiedad <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4610b-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="4610b-112">Rechazar la nueva normalización de la ruta de acceso mediante el establecimiento del conmutador `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> en `true`.</span><span class="sxs-lookup"><span data-stu-id="4610b-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4610b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4610b-113">See also</span></span>

- [<span data-ttu-id="4610b-114">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="4610b-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
