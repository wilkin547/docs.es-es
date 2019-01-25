---
title: Procedimiento Aplicar un objeto GuidelineSet a un dibujo
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 4bd2ee349f2c1855a9af6b4c00f2630cd50a9108
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493383"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="a43ce-102">Procedimiento Aplicar un objeto GuidelineSet a un dibujo</span><span class="sxs-lookup"><span data-stu-id="a43ce-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="a43ce-103">En este ejemplo se muestra cómo aplicar un <xref:System.Windows.Media.GuidelineSet> a un <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="a43ce-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="a43ce-104">El <xref:System.Windows.Media.DrawingGroup> clase es el único tipo de <xref:System.Windows.Media.Drawing> que tiene un <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a43ce-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="a43ce-105">Para aplicar un <xref:System.Windows.Media.GuidelineSet> a otro tipo de <xref:System.Windows.Media.Drawing>, agréguela a un <xref:System.Windows.Media.DrawingGroup> y, a continuación, aplicar el <xref:System.Windows.Media.GuidelineSet> a su <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="a43ce-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a43ce-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a43ce-106">Example</span></span>  
 <span data-ttu-id="a43ce-107">En el ejemplo siguiente se crean dos <xref:System.Windows.Media.DrawingGroup> objetos que son casi idénticos; la única diferencia es: el segundo <xref:System.Windows.Media.DrawingGroup> tiene un <xref:System.Windows.Media.GuidelineSet> y no el primero.</span><span class="sxs-lookup"><span data-stu-id="a43ce-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="a43ce-108">En la siguiente ilustración se muestra el resultado del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a43ce-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="a43ce-109">Dado que la representación de las diferencias entre los dos <xref:System.Windows.Media.DrawingGroup> objetos es muy sutil, se amplían partes de los dibujos.</span><span class="sxs-lookup"><span data-stu-id="a43ce-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="a43ce-110">![DrawingGroup con y sin GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="a43ce-110">![A DrawingGroup with and without a GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a43ce-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a43ce-111">See also</span></span>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [<span data-ttu-id="a43ce-112">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="a43ce-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
