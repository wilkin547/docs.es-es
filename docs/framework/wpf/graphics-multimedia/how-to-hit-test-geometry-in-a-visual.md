---
title: Procedimiento Geometría de una prueba de posicionamiento en un objeto visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 87b626e575d889447ef061d1ed62ef28efe5dfeb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227345"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="2ec71-102">Procedimiento Geometría de una prueba de posicionamiento en un objeto visual</span><span class="sxs-lookup"><span data-stu-id="2ec71-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="2ec71-103">En este ejemplo se muestra cómo realizar una prueba de posicionamiento en un objeto visual que se compone de uno o varios <xref:System.Windows.Media.Geometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="2ec71-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ec71-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ec71-104">Example</span></span>  
 <span data-ttu-id="2ec71-105">El ejemplo siguiente muestra cómo recuperar el <xref:System.Windows.Media.DrawingGroup> desde un objeto visual que utiliza el <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> método.</span><span class="sxs-lookup"><span data-stu-id="2ec71-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="2ec71-106">A continuación, se realiza una prueba de posicionamiento en el contenido representado de cada dibujo de la <xref:System.Windows.Media.DrawingGroup> para determinar qué geometría se posicionó.</span><span class="sxs-lookup"><span data-stu-id="2ec71-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ec71-107">En la mayoría de los casos, se utilizaría el <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método para determinar si un punto corta el contenido representado de un objeto visual.</span><span class="sxs-lookup"><span data-stu-id="2ec71-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="2ec71-108">El <xref:System.Windows.Media.Geometry.FillContains%2A> método es un método sobrecargado que permite realizar pruebas de posicionamiento mediante el uso de un determinado <xref:System.Windows.Point> o <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="2ec71-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="2ec71-109">Si se traza una geometría, el trazo puede extenderse fuera del límite del relleno.</span><span class="sxs-lookup"><span data-stu-id="2ec71-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="2ec71-110">En este caso, es posible que desea llamar <xref:System.Windows.Media.Geometry.StrokeContains%2A> además <xref:System.Windows.Media.Geometry.FillContains%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ec71-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="2ec71-111">También puede proporcionar un <xref:System.Windows.Media.ToleranceType> que se usa para los fines de aplanamiento de Bezier.</span><span class="sxs-lookup"><span data-stu-id="2ec71-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ec71-112">Esta muestra no tiene en cuenta ninguna transformación o recorte que pueda aplicarse a la geometría.</span><span class="sxs-lookup"><span data-stu-id="2ec71-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="2ec71-113">Además, este ejemplo no funcionará con un control con estilo, puesto que no tiene los dibujos asociados a él.</span><span class="sxs-lookup"><span data-stu-id="2ec71-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec71-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ec71-114">See also</span></span>

- [<span data-ttu-id="2ec71-115">Realizar pruebas de posicionamiento en la capa visual</span><span class="sxs-lookup"><span data-stu-id="2ec71-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="2ec71-116">Realizar una prueba de posicionamiento usando Geometry como parámetro</span><span class="sxs-lookup"><span data-stu-id="2ec71-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
