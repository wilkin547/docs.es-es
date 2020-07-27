---
title: Optimizar el rendimiento de la aplicación
description: Utilice estos recursos para mejorar el rendimiento de las aplicaciones Windows Presentation Foundation, como planear el rendimiento y aprovechar el hardware.
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 165caaf102a66988db0254839a947b8e262a386d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166330"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="1d6b7-103">Optimizar WPF: Rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1d6b7-103">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="1d6b7-104">Esta sección está pensada como una referencia para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] los desarrolladores de aplicaciones que buscan maneras de mejorar el rendimiento de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-104">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="1d6b7-105">Si es un desarrollador que es nuevo en el marco de trabajo de Microsoft .NET y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , primero debe familiarizarse con ambas plataformas.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-105">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="1d6b7-106">En esta sección se da por supuesto que tiene conocimientos prácticos de ambos y está escrito para los programadores que ya saben lo suficiente para poner en marcha sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-106">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d6b7-107">Los datos de rendimiento que se proporcionan en esta sección se basan en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones que se ejecutan en un equipo 2,8 GHz con 512 de RAM y una tarjeta gráfica ATI Radeon 9700.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-107">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d6b7-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1d6b7-108">In This Section</span></span>  
 [<span data-ttu-id="1d6b7-109">Planear para mejorar el rendimiento de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1d6b7-109">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="1d6b7-110">Aprovechar el hardware</span><span class="sxs-lookup"><span data-stu-id="1d6b7-110">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="1d6b7-111">Presentación y diseño</span><span class="sxs-lookup"><span data-stu-id="1d6b7-111">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="1d6b7-112">Imágenes y gráficos 2D</span><span class="sxs-lookup"><span data-stu-id="1d6b7-112">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="1d6b7-113">Comportamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="1d6b7-113">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="1d6b7-114">Recursos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="1d6b7-114">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="1d6b7-115">Texto</span><span class="sxs-lookup"><span data-stu-id="1d6b7-115">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="1d6b7-116">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="1d6b7-116">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="1d6b7-117">Controles</span><span class="sxs-lookup"><span data-stu-id="1d6b7-117">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="1d6b7-118">Otras recomendaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="1d6b7-118">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="1d6b7-119">Tiempo de inicio de una aplicación</span><span class="sxs-lookup"><span data-stu-id="1d6b7-119">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d6b7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d6b7-120">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="1d6b7-121">Niveles de representación de gráficos</span><span class="sxs-lookup"><span data-stu-id="1d6b7-121">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="1d6b7-122">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="1d6b7-122">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="1d6b7-123">Diseño</span><span class="sxs-lookup"><span data-stu-id="1d6b7-123">Layout</span></span>](layout.md)
- [<span data-ttu-id="1d6b7-124">Árboles en WPF</span><span class="sxs-lookup"><span data-stu-id="1d6b7-124">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="1d6b7-125">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="1d6b7-125">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="1d6b7-126">Usar objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="1d6b7-126">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="1d6b7-127">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="1d6b7-127">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="1d6b7-128">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="1d6b7-128">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="1d6b7-129">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="1d6b7-129">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="1d6b7-130">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="1d6b7-130">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="1d6b7-131">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="1d6b7-131">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="1d6b7-132">Tipografía en WPF</span><span class="sxs-lookup"><span data-stu-id="1d6b7-132">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="1d6b7-133">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="1d6b7-133">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="1d6b7-134">Información general sobre navegación</span><span class="sxs-lookup"><span data-stu-id="1d6b7-134">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="1d6b7-135">Sugerencias y trucos para animaciones</span><span class="sxs-lookup"><span data-stu-id="1d6b7-135">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="1d6b7-136">Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="1d6b7-136">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
