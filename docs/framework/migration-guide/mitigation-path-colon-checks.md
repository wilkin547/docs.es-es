---
title: 'Mitigación: comprobaciones de dos puntos en las rutas de acceso'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: e88643fea3bd507289436f41880a2de34117884f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457899"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="f7ddd-102">Mitigación: comprobaciones de dos puntos en las rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="f7ddd-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="f7ddd-103">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, se han realizado una serie de cambios para admitir rutas de acceso que anteriormente no se admitían (en términos de longitud y formato).</span><span class="sxs-lookup"><span data-stu-id="f7ddd-103">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="f7ddd-104">En concreto, las comprobaciones de la sintaxis de separador de la unidad correspondiente (dos puntos) se realizan de manera más correcta.</span><span class="sxs-lookup"><span data-stu-id="f7ddd-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="f7ddd-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="f7ddd-105">Impact</span></span>  
 <span data-ttu-id="f7ddd-106">Estos cambios bloquean algunas rutas del identificador URI que los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> admitían anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f7ddd-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="f7ddd-107">Mitigación</span><span class="sxs-lookup"><span data-stu-id="f7ddd-107">Mitigation</span></span>  
 <span data-ttu-id="f7ddd-108">Para solucionar el problema de una ruta de acceso anteriormente aceptable que ya no es compatible con los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, puede llevar a cabo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7ddd-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="f7ddd-109">Quitar manualmente el esquema de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f7ddd-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="f7ddd-110">Por ejemplo, quitar `file://` de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f7ddd-110">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="f7ddd-111">Pasar el identificador URI al constructor <xref:System.Uri> y recuperar el valor de la propiedad <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f7ddd-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="f7ddd-112">Rechazar la nueva normalización de la ruta de acceso mediante el establecimiento del conmutador `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> en `true`.</span><span class="sxs-lookup"><span data-stu-id="f7ddd-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f7ddd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7ddd-113">See also</span></span>

- [<span data-ttu-id="f7ddd-114">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f7ddd-114">Application compatibility</span></span>](application-compatibility.md)
