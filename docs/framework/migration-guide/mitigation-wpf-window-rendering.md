---
title: 'Mitigación: representación de ventanas de WPF'
description: Obtenga información sobre el impacto y la mitigación de la representación de ventanas de WPF en .NET Framework 4.6 cuando se ejecuta en Windows 8 o versiones posteriores.
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
ms.openlocfilehash: d624478d17a4076107438f71b0a86eeb6d9f3ea4
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475338"
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="fbe6b-103">Mitigación: representación de ventanas de WPF</span><span class="sxs-lookup"><span data-stu-id="fbe6b-103">Mitigation: WPF Window Rendering</span></span>

<span data-ttu-id="fbe6b-104">En .NET Framework 4.6 ejecutado en Windows 8 y versiones posteriores, se representa toda la ventana sin recortes cuando se amplía más allá de una única pantalla en un escenario de varios monitores.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-104">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>

## <a name="impact"></a><span data-ttu-id="fbe6b-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="fbe6b-105">Impact</span></span>

<span data-ttu-id="fbe6b-106">En general, la representación de una ventana completa en varios monitores sin recortes es el comportamiento esperado.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-106">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="fbe6b-107">Sin embargo, en Windows 7 y en versiones anteriores, las ventanas de WPF se recortan al extenderse más allá de una sola pantalla, ya que la representación de una parte de la ventana en el segundo monitor tiene un impacto considerable en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-107">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>

<span data-ttu-id="fbe6b-108">El impacto preciso de la representación de ventanas de WPF en varios monitores con Windows 8 y versiones posteriores no se puede cuantificar de forma precisa, ya que depende de muchos factores.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-108">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="fbe6b-109">En algunos casos podría producir un impacto negativo en el rendimiento, sobre todo para los usuarios que ejecutan aplicaciones con muchos gráficos y que tienen ventanas que ocupan varios monitores.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-109">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="fbe6b-110">En otros casos, puede que lo único que quiera es tener un comportamiento constante en todas las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-110">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>

## <a name="mitigation"></a><span data-ttu-id="fbe6b-111">Mitigación</span><span class="sxs-lookup"><span data-stu-id="fbe6b-111">Mitigation</span></span>

<span data-ttu-id="fbe6b-112">Puede deshabilitar este cambio y volver al comportamiento anterior, en el que se recorta una ventana de WPF al extenderse más allá de una pantalla.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-112">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="fbe6b-113">Existen dos modos para hacer esto:</span><span class="sxs-lookup"><span data-stu-id="fbe6b-113">There are two ways to do this:</span></span>

- <span data-ttu-id="fbe6b-114">Puede agregar el elemento `<EnableMultiMonitorDisplayClipping>` a la sección `<appSettings>` del archivo de configuración de la aplicación para habilitar o deshabilitar este comportamiento en las aplicaciones que se ejecutan en Windows 8 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-114">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="fbe6b-115">Por ejemplo, la siguiente sección de configuración deshabilita la representación sin recortes:</span><span class="sxs-lookup"><span data-stu-id="fbe6b-115">For example, the following configuration section disables rendering without clipping:</span></span>

  ```xml
  <appSettings>
      <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    </appSettings>
  ```

  <span data-ttu-id="fbe6b-116">La opción de configuración `<EnableMultiMonitorDisplayClipping>` puede tener cualquiera de estos dos valores:</span><span class="sxs-lookup"><span data-stu-id="fbe6b-116">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>

  - <span data-ttu-id="fbe6b-117">`true` para habilitar el recorte de ventanas para supervisar los límites durante la representación.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-117">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>

  - <span data-ttu-id="fbe6b-118">`false` para deshabilitar el recorte de ventanas para supervisar los límites durante la representación.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-118">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>

- <span data-ttu-id="fbe6b-119">Estableciendo la propiedad <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> en `true` al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fbe6b-119">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbe6b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbe6b-120">See also</span></span>

- [<span data-ttu-id="fbe6b-121">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fbe6b-121">Application compatibility</span></span>](application-compatibility.md)
