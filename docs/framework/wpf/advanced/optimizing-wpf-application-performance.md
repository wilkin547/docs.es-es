---
title: Optimizar el rendimiento de la aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: cc6ea051401199a87965565c920068fd55cb05d0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743949"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="282e5-102">Optimizar WPF: Rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="282e5-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="282e5-103">Esta sección está pensada como una referencia para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] desarrolladores de aplicaciones que buscan maneras de mejorar el rendimiento de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="282e5-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="282e5-104">Si es un desarrollador que es nuevo en el marco de Microsoft .NET y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], primero debe familiarizarse con ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="282e5-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="282e5-105">En esta sección se da por supuesto que tiene conocimientos prácticos de ambos y está escrito para los programadores que ya saben lo suficiente para poner en marcha sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="282e5-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="282e5-106">Los datos de rendimiento que se proporcionan en esta sección se basan en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones que se ejecutan en un equipo 2,8 GHz con 512 de RAM y una tarjeta gráfica ATI Radeon 9700.</span><span class="sxs-lookup"><span data-stu-id="282e5-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="282e5-107">Esta sección</span><span class="sxs-lookup"><span data-stu-id="282e5-107">In This Section</span></span>  
 [<span data-ttu-id="282e5-108">Planear para mejorar el rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="282e5-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="282e5-109">Aprovechar el hardware</span><span class="sxs-lookup"><span data-stu-id="282e5-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="282e5-110">Presentación y diseño</span><span class="sxs-lookup"><span data-stu-id="282e5-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="282e5-111">Imágenes y gráficos 2D</span><span class="sxs-lookup"><span data-stu-id="282e5-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="282e5-112">Comportamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="282e5-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="282e5-113">Recursos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="282e5-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="282e5-114">Text</span><span class="sxs-lookup"><span data-stu-id="282e5-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="282e5-115">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="282e5-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="282e5-116">Controles</span><span class="sxs-lookup"><span data-stu-id="282e5-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="282e5-117">Otras recomendaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="282e5-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="282e5-118">Tiempo de inicio de una aplicación</span><span class="sxs-lookup"><span data-stu-id="282e5-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="282e5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="282e5-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="282e5-120">Niveles de representación de gráficos</span><span class="sxs-lookup"><span data-stu-id="282e5-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="282e5-121">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="282e5-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="282e5-122">Diseño</span><span class="sxs-lookup"><span data-stu-id="282e5-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="282e5-123">Árboles en WPF</span><span class="sxs-lookup"><span data-stu-id="282e5-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="282e5-124">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="282e5-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="282e5-125">Usar objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="282e5-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="282e5-126">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="282e5-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="282e5-127">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="282e5-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="282e5-128">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="282e5-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="282e5-129">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="282e5-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="282e5-130">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="282e5-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="282e5-131">Tipografía en WPF</span><span class="sxs-lookup"><span data-stu-id="282e5-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="282e5-132">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="282e5-132">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="282e5-133">Información general sobre navegación</span><span class="sxs-lookup"><span data-stu-id="282e5-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="282e5-134">Sugerencias y trucos para animaciones</span><span class="sxs-lookup"><span data-stu-id="282e5-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="282e5-135">Tutorial: Almacenar en caché datos de la aplicación en una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="282e5-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
