---
title: 'Optimizar WPF: Rendimiento de aplicaciones'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
caps.latest.revision: "45"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 385bcb8678b11e1cb8f84ae509b1f1b6777665d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="f4497-102">Optimizar WPF: Rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f4497-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="f4497-103">Esta sección sirve como referencia para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] los desarrolladores de aplicaciones que están buscando maneras de mejorar el rendimiento de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4497-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="f4497-104">Si es un desarrollador que está familiarizado con la [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], primero debe familiarizarse con ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="f4497-104">If you are a developer who is new to the [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="f4497-105">En esta sección se da por supuesto conocimientos prácticos de ambos y se escribe para los programadores que ya sabe lo suficiente como para ponerse en marcha sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4497-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4497-106">Los datos de rendimiento proporcionados en esta sección se basan en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones que se ejecutan en un PC a 2,8 GHz con 512 de RAM y una ATI Radeon 9700 tarjeta gráfica.</span><span class="sxs-lookup"><span data-stu-id="f4497-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4497-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f4497-107">In This Section</span></span>  
 [<span data-ttu-id="f4497-108">Planear para mejorar el rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f4497-108">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [<span data-ttu-id="f4497-109">Aprovechar el hardware</span><span class="sxs-lookup"><span data-stu-id="f4497-109">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="f4497-110">Presentación y diseño</span><span class="sxs-lookup"><span data-stu-id="f4497-110">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="f4497-111">Imágenes y gráficos 2D</span><span class="sxs-lookup"><span data-stu-id="f4497-111">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="f4497-112">Comportamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="f4497-112">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="f4497-113">Recursos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f4497-113">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="f4497-114">Texto</span><span class="sxs-lookup"><span data-stu-id="f4497-114">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [<span data-ttu-id="f4497-115">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f4497-115">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="f4497-116">Controles</span><span class="sxs-lookup"><span data-stu-id="f4497-116">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [<span data-ttu-id="f4497-117">Otras recomendaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="f4497-117">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="f4497-118">Tiempo de inicio de una aplicación</span><span class="sxs-lookup"><span data-stu-id="f4497-118">Application Startup Time</span></span>](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="f4497-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4497-119">See Also</span></span>  
 <xref:System.Windows.Media.RenderOptions>  
 <xref:System.Windows.Media.RenderCapability>  
 [<span data-ttu-id="f4497-120">Niveles de representación de gráficos</span><span class="sxs-lookup"><span data-stu-id="f4497-120">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)  
 [<span data-ttu-id="f4497-121">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="f4497-121">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="f4497-122">Diseño</span><span class="sxs-lookup"><span data-stu-id="f4497-122">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
 [<span data-ttu-id="f4497-123">Árboles en WPF</span><span class="sxs-lookup"><span data-stu-id="f4497-123">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [<span data-ttu-id="f4497-124">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="f4497-124">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="f4497-125">Usar objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="f4497-125">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)  
 [<span data-ttu-id="f4497-126">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="f4497-126">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="f4497-127">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="f4497-127">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="f4497-128">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="f4497-128">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="f4497-129">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="f4497-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="f4497-130">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="f4497-130">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [<span data-ttu-id="f4497-131">Tipografía en WPF</span><span class="sxs-lookup"><span data-stu-id="f4497-131">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="f4497-132">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f4497-132">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f4497-133">Información general sobre navegación</span><span class="sxs-lookup"><span data-stu-id="f4497-133">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [<span data-ttu-id="f4497-134">Sugerencias y trucos para animaciones</span><span class="sxs-lookup"><span data-stu-id="f4497-134">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)  
 [<span data-ttu-id="f4497-135">Tutorial: Almacenar en caché datos de la aplicación en una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="f4497-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
