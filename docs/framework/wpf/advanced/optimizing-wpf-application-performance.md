---
title: 'Optimizar WPF: Rendimiento de aplicaciones'
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: c1dd2587fb3642fb930fb7d5d6855a6e48c2ad2b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356395"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="fc37c-102">Optimizar WPF: Rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fc37c-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="fc37c-103">En esta sección sirve como referencia para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] los desarrolladores de aplicaciones que están buscando maneras de mejorar el rendimiento de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fc37c-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="fc37c-104">Si es un desarrollador que está familiarizado con Microsoft .NET Framework y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], primero debe familiarizarse con ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="fc37c-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="fc37c-105">En esta sección se da por supuesto conocimientos prácticos de ambos y se escribe para los programadores que ya sabe lo suficiente para ponerse en marcha sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fc37c-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc37c-106">Los datos de rendimiento proporcionados en esta sección se basan en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones que se ejecutan en un PC a 2,8 GHz con 512 RAM y una ATI Radeon 9700 tarjeta gráfica.</span><span class="sxs-lookup"><span data-stu-id="fc37c-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc37c-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fc37c-107">In This Section</span></span>  
 [<span data-ttu-id="fc37c-108">Planear para mejorar el rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fc37c-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="fc37c-109">Aprovechar el hardware</span><span class="sxs-lookup"><span data-stu-id="fc37c-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="fc37c-110">Presentación y diseño</span><span class="sxs-lookup"><span data-stu-id="fc37c-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="fc37c-111">Imágenes y gráficos 2D</span><span class="sxs-lookup"><span data-stu-id="fc37c-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="fc37c-112">Comportamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="fc37c-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="fc37c-113">Recursos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="fc37c-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="fc37c-114">Texto</span><span class="sxs-lookup"><span data-stu-id="fc37c-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="fc37c-115">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="fc37c-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="fc37c-116">Controles</span><span class="sxs-lookup"><span data-stu-id="fc37c-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="fc37c-117">Otras recomendaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="fc37c-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="fc37c-118">Tiempo de inicio de una aplicación</span><span class="sxs-lookup"><span data-stu-id="fc37c-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc37c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc37c-119">See also</span></span>
- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="fc37c-120">Niveles de representación de gráficos</span><span class="sxs-lookup"><span data-stu-id="fc37c-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="fc37c-121">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="fc37c-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="fc37c-122">Diseño</span><span class="sxs-lookup"><span data-stu-id="fc37c-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="fc37c-123">Árboles en WPF</span><span class="sxs-lookup"><span data-stu-id="fc37c-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="fc37c-124">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="fc37c-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="fc37c-125">Usar objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="fc37c-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="fc37c-126">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="fc37c-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="fc37c-127">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="fc37c-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="fc37c-128">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="fc37c-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="fc37c-129">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="fc37c-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="fc37c-130">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="fc37c-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="fc37c-131">Tipografía en WPF</span><span class="sxs-lookup"><span data-stu-id="fc37c-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="fc37c-132">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="fc37c-132">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="fc37c-133">Información general sobre navegación</span><span class="sxs-lookup"><span data-stu-id="fc37c-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="fc37c-134">Sugerencias y trucos para animaciones</span><span class="sxs-lookup"><span data-stu-id="fc37c-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="fc37c-135">Tutorial: Almacenamiento en caché datos de la aplicación en una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="fc37c-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
