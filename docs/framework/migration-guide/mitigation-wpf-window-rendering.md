---
title: "Mitigación: representación de ventanas de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 032d07b75b96809ff71c7735a267a7351ad25dda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="1fa94-102">Mitigación: representación de ventanas de WPF</span><span class="sxs-lookup"><span data-stu-id="1fa94-102">Mitigation: WPF Window Rendering</span></span>
<span data-ttu-id="1fa94-103">En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], ejecutado en Windows 8 y versiones posteriores, la ventana en su totalidad se representa sin recortes al extenderse más allá de una sola pantalla en un escenario de varios monitores.</span><span class="sxs-lookup"><span data-stu-id="1fa94-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="1fa94-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="1fa94-104">Impact</span></span>  
 <span data-ttu-id="1fa94-105">En general, la representación de una ventana completa en varios monitores sin recortes es el comportamiento esperado.</span><span class="sxs-lookup"><span data-stu-id="1fa94-105">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="1fa94-106">Sin embargo, en Windows 7 y en versiones anteriores, las ventanas de WPF se recortan al extenderse más allá de una sola pantalla, ya que la representación de una parte de la ventana en el segundo monitor tiene un impacto considerable en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1fa94-106">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>  
  
 <span data-ttu-id="1fa94-107">El impacto preciso de la representación de ventanas de WPF en varios monitores con Windows 8 y versiones posteriores no se puede cuantificar de forma precisa, ya que depende de muchos factores.</span><span class="sxs-lookup"><span data-stu-id="1fa94-107">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="1fa94-108">En algunos casos podría producir un impacto negativo en el rendimiento, sobre todo para los usuarios que ejecutan aplicaciones con muchos gráficos y que tienen ventanas que ocupan varios monitores.</span><span class="sxs-lookup"><span data-stu-id="1fa94-108">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="1fa94-109">En otros casos, puede que lo único que quiera es tener un comportamiento constante en todas las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1fa94-109">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="1fa94-110">Mitigación</span><span class="sxs-lookup"><span data-stu-id="1fa94-110">Mitigation</span></span>  
 <span data-ttu-id="1fa94-111">Puede deshabilitar este cambio y volver al comportamiento anterior, en el que se recorta una ventana de WPF al extenderse más allá de una pantalla.</span><span class="sxs-lookup"><span data-stu-id="1fa94-111">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="1fa94-112">Existen dos modos para hacer esto:</span><span class="sxs-lookup"><span data-stu-id="1fa94-112">There are two ways to do this:</span></span>  
  
-   <span data-ttu-id="1fa94-113">Puede agregar el elemento `<EnableMultiMonitorDisplayClipping>` a la sección `<appSettings>` del archivo de configuración de la aplicación para habilitar o deshabilitar este comportamiento en las aplicaciones que se ejecutan en Windows 8 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1fa94-113">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="1fa94-114">Por ejemplo, la siguiente sección de configuración deshabilita la representación sin recortes:</span><span class="sxs-lookup"><span data-stu-id="1fa94-114">For example, the following configuration section disables rendering without clipping:</span></span>  
  
    ```xml  
    <appSettings>  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
      </appSettings>  
    ```  
  
     <span data-ttu-id="1fa94-115">La opción de configuración `<EnableMultiMonitorDisplayClipping>` puede tener cualquiera de estos dos valores:</span><span class="sxs-lookup"><span data-stu-id="1fa94-115">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>  
  
    -   <span data-ttu-id="1fa94-116">`true` para habilitar el recorte de ventanas para supervisar los límites durante la representación.</span><span class="sxs-lookup"><span data-stu-id="1fa94-116">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>  
  
    -   <span data-ttu-id="1fa94-117">`false` para deshabilitar el recorte de ventanas para supervisar los límites durante la representación.</span><span class="sxs-lookup"><span data-stu-id="1fa94-117">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>  
  
-   <span data-ttu-id="1fa94-118">Estableciendo la propiedad <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> en `true` al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1fa94-118">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa94-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fa94-119">See Also</span></span>  
 [<span data-ttu-id="1fa94-120">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="1fa94-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
