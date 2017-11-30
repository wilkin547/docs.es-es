---
title: "Mitigación: diseño de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3ba5ac792169cc076f9621025f35444281cec6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="cfb1a-102">Mitigación: diseño de WPF</span><span class="sxs-lookup"><span data-stu-id="cfb1a-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="cfb1a-103">El diseño de los controles WPF puede cambiar ligeramente.</span><span class="sxs-lookup"><span data-stu-id="cfb1a-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="cfb1a-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="cfb1a-104">Impact</span></span>  
 <span data-ttu-id="cfb1a-105">Debido a este cambio:</span><span class="sxs-lookup"><span data-stu-id="cfb1a-105">As a result of this change:</span></span>  
  
-   <span data-ttu-id="cfb1a-106">El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.</span><span class="sxs-lookup"><span data-stu-id="cfb1a-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
-   <span data-ttu-id="cfb1a-107">La posición de un objeto se puede mover un píxel como máximo.</span><span class="sxs-lookup"><span data-stu-id="cfb1a-107">The placement of an object can move by at most one pixel.</span></span>  
  
-   <span data-ttu-id="cfb1a-108">Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.</span><span class="sxs-lookup"><span data-stu-id="cfb1a-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="cfb1a-109">De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="cfb1a-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="cfb1a-110">Mitigación</span><span class="sxs-lookup"><span data-stu-id="cfb1a-110">Mitigation</span></span>  
 <span data-ttu-id="cfb1a-111">Dado que esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="cfb1a-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="cfb1a-112">Las aplicaciones que tienen como destino .NET Framework 4.6 y que desean que los controles WPF efectúen la representación con el algoritmo de diseño anterior pueden hacerlo agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="cfb1a-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfb1a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfb1a-113">See Also</span></span>  
 [<span data-ttu-id="cfb1a-114">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="cfb1a-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
