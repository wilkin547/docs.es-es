---
title: "Cómo: Crear una geometría combinada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee77da00604b7e4965cc376748606b6bd0e92ad8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="0af05-102">Cómo: Crear una geometría combinada</span><span class="sxs-lookup"><span data-stu-id="0af05-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="0af05-103">En este ejemplo se muestra cómo combinar las geometrías.</span><span class="sxs-lookup"><span data-stu-id="0af05-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="0af05-104">Para combinar dos geometrías, utilice un <xref:System.Windows.Media.CombinedGeometry> objeto.</span><span class="sxs-lookup"><span data-stu-id="0af05-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="0af05-105">Establecer su <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> propiedades con las dos geometrías para combinar y establecer el <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> propiedad, que determina cómo las geometrías se combinan entre sí, para `Union`, `Intersect`, `Exclude`, o `Xor`.</span><span class="sxs-lookup"><span data-stu-id="0af05-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="0af05-106">Para crear una geometría compuesta de dos o más objetos Geometry, use un <xref:System.Windows.Media.GeometryGroup>.</span><span class="sxs-lookup"><span data-stu-id="0af05-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0af05-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0af05-107">Example</span></span>  
 <span data-ttu-id="0af05-108">En el ejemplo siguiente, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación de geometría de `Exclude`.</span><span class="sxs-lookup"><span data-stu-id="0af05-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="0af05-109">Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.</span><span class="sxs-lookup"><span data-stu-id="0af05-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="0af05-110">![Modo de combinación de resultados de la exclusión](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="0af05-110">![Results of the Exclude combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="0af05-111">Exclusión de geometría combinada</span><span class="sxs-lookup"><span data-stu-id="0af05-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="0af05-112">En el siguiente código de marcado, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Intersect`.</span><span class="sxs-lookup"><span data-stu-id="0af05-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="0af05-113">Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.</span><span class="sxs-lookup"><span data-stu-id="0af05-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="0af05-114">![Modo de combinación de resultados de la intersección](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="0af05-114">![Results of the Intersect combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="0af05-115">Geometría combinada forman una intersección</span><span class="sxs-lookup"><span data-stu-id="0af05-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="0af05-116">En el siguiente código de marcado, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Union`.</span><span class="sxs-lookup"><span data-stu-id="0af05-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="0af05-117">Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.</span><span class="sxs-lookup"><span data-stu-id="0af05-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="0af05-118">![Resultados del modo de combinación Union](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="0af05-118">![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="0af05-119">Unión de geometría combinada</span><span class="sxs-lookup"><span data-stu-id="0af05-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="0af05-120">En el siguiente código de marcado, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación `Xor`.</span><span class="sxs-lookup"><span data-stu-id="0af05-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="0af05-121">Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.</span><span class="sxs-lookup"><span data-stu-id="0af05-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="0af05-122">![Resultados del modo de combinación Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="0af05-122">![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="0af05-123">Geometría combinada Xor</span><span class="sxs-lookup"><span data-stu-id="0af05-123">Combined Geometry Xor</span></span>
