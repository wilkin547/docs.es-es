---
title: "Cómo: Geometría de una prueba de seguimiento en un objeto visual"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a990a43853e375c1c97f88dc6792932ad64c8d37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="3eec8-102">Cómo: Geometría de una prueba de seguimiento en un objeto visual</span><span class="sxs-lookup"><span data-stu-id="3eec8-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="3eec8-103">Este ejemplo muestra cómo realizar una prueba de posicionamiento en un objeto visual que se compone de uno o varios <xref:System.Windows.Media.Geometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="3eec8-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eec8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3eec8-104">Example</span></span>  
 <span data-ttu-id="3eec8-105">En el ejemplo siguiente se muestra cómo recuperar el <xref:System.Windows.Media.DrawingGroup> desde un objeto visual que usa el <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> método.</span><span class="sxs-lookup"><span data-stu-id="3eec8-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="3eec8-106">A continuación, se realiza una prueba de posicionamiento en el contenido representado de cada dibujo el <xref:System.Windows.Media.DrawingGroup> para determinar qué geometría se obtuvo acceso.</span><span class="sxs-lookup"><span data-stu-id="3eec8-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3eec8-107">En la mayoría de los casos, se utilizaría la <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método para determinar si un punto forma una intersección con el contenido representado de un objeto visual.</span><span class="sxs-lookup"><span data-stu-id="3eec8-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="3eec8-108">El <xref:System.Windows.Media.Geometry.FillContains%2A> método es un método sobrecargado que permite realizar pruebas de posicionamiento mediante el uso de un determinado <xref:System.Windows.Point> o <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="3eec8-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="3eec8-109">Si se traza una geometría, el trazo puede extenderse fuera del límite del relleno.</span><span class="sxs-lookup"><span data-stu-id="3eec8-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="3eec8-110">En este caso, puede que desee llamar a <xref:System.Windows.Media.Geometry.StrokeContains%2A> además <xref:System.Windows.Media.Geometry.FillContains%2A>.</span><span class="sxs-lookup"><span data-stu-id="3eec8-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="3eec8-111">También puede proporcionar un <xref:System.Windows.Media.ToleranceType> que se usa para los propósitos de reducción de Bézier.</span><span class="sxs-lookup"><span data-stu-id="3eec8-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3eec8-112">Esta muestra no tiene en cuenta ninguna transformación o recorte que pueda aplicarse a la geometría.</span><span class="sxs-lookup"><span data-stu-id="3eec8-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="3eec8-113">Además, este ejemplo no funcionará con un control con estilo, puesto que no tiene los dibujos asociados a él.</span><span class="sxs-lookup"><span data-stu-id="3eec8-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eec8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eec8-114">See Also</span></span>  
 [<span data-ttu-id="3eec8-115">Realizar pruebas de posicionamiento en la capa visual</span><span class="sxs-lookup"><span data-stu-id="3eec8-115">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="3eec8-116">Realizar una prueba de posicionamiento usando Geometry como parámetro</span><span class="sxs-lookup"><span data-stu-id="3eec8-116">Hit Test Using Geometry as a Parameter</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)
