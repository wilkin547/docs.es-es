---
title: 'Mitigación: comprobaciones de dos puntos en las rutas de acceso'
description: Obtenga información sobre los cambios realizados en .NET Framework 4.6.2 para admitir comprobaciones de la sintaxis correcta de los separadores de unidad (los dos puntos).
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: 03f1c7249549aae7e3bef986c97fb5f320fbeb2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283463"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="e1458-103">Mitigación: comprobaciones de dos puntos en las rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="e1458-103">Mitigation: Path Colon Checks</span></span>

<span data-ttu-id="e1458-104">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, se han realizado una serie de cambios para admitir rutas de acceso que anteriormente no se admitían (en términos de longitud y formato).</span><span class="sxs-lookup"><span data-stu-id="e1458-104">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="e1458-105">En concreto, las comprobaciones de la sintaxis de separador de la unidad correspondiente (dos puntos) se realizan de manera más correcta.</span><span class="sxs-lookup"><span data-stu-id="e1458-105">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e1458-106">Impacto</span><span class="sxs-lookup"><span data-stu-id="e1458-106">Impact</span></span>  

 <span data-ttu-id="e1458-107">Estos cambios bloquean algunas rutas del identificador URI que los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> admitían anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e1458-107">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e1458-108">Mitigación</span><span class="sxs-lookup"><span data-stu-id="e1458-108">Mitigation</span></span>  

 <span data-ttu-id="e1458-109">Para solucionar el problema de una ruta de acceso anteriormente aceptable que ya no es compatible con los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, puede llevar a cabo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1458-109">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="e1458-110">Quitar manualmente el esquema de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="e1458-110">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="e1458-111">Por ejemplo, quitar `file://` de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="e1458-111">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="e1458-112">Pasar el identificador URI al constructor <xref:System.Uri> y recuperar el valor de la propiedad <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e1458-112">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="e1458-113">Rechazar la nueva normalización de la ruta de acceso mediante el establecimiento del conmutador `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> en `true`.</span><span class="sxs-lookup"><span data-stu-id="e1458-113">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e1458-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1458-114">See also</span></span>

- [<span data-ttu-id="e1458-115">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e1458-115">Application compatibility</span></span>](application-compatibility.md)
