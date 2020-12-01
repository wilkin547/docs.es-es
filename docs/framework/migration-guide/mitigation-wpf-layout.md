---
title: 'Mitigación: diseño de WPF'
description: Obtenga información sobre cómo mitigar los problemas derivados de un cambio en el diseño de los controles de WPF, como el desplazamiento en un píxel de la posición de un objeto.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: caed758f6e86a1e2bee255c2f29ca3160b327e17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244085"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="2228c-103">Mitigación: Diseño de WPF</span><span class="sxs-lookup"><span data-stu-id="2228c-103">Mitigation: WPF Layout</span></span>

<span data-ttu-id="2228c-104">El diseño de los controles WPF puede cambiar ligeramente.</span><span class="sxs-lookup"><span data-stu-id="2228c-104">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="2228c-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="2228c-105">Impact</span></span>  

 <span data-ttu-id="2228c-106">Debido a este cambio:</span><span class="sxs-lookup"><span data-stu-id="2228c-106">As a result of this change:</span></span>  
  
- <span data-ttu-id="2228c-107">El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.</span><span class="sxs-lookup"><span data-stu-id="2228c-107">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="2228c-108">La posición de un objeto se puede mover un píxel como máximo.</span><span class="sxs-lookup"><span data-stu-id="2228c-108">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="2228c-109">Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.</span><span class="sxs-lookup"><span data-stu-id="2228c-109">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="2228c-110">De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="2228c-110">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="2228c-111">Mitigación</span><span class="sxs-lookup"><span data-stu-id="2228c-111">Mitigation</span></span>  

 <span data-ttu-id="2228c-112">Dado que esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="2228c-112">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="2228c-113">Las aplicaciones que tienen como destino .NET Framework 4.6 y que desean que los controles WPF efectúen la representación con el algoritmo de diseño anterior pueden hacerlo agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="2228c-113">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="2228c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2228c-114">See also</span></span>

- [<span data-ttu-id="2228c-115">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2228c-115">Application compatibility</span></span>](application-compatibility.md)
