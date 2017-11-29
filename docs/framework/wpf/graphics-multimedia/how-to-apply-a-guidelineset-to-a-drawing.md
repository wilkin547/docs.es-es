---
title: "Cómo: Aplicar un objeto GuidelineSet a un dibujo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd8d93d128c03cb9ee482860603e5734e96c6fc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="51e6e-102">Cómo: Aplicar un objeto GuidelineSet a un dibujo</span><span class="sxs-lookup"><span data-stu-id="51e6e-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="51e6e-103">Este ejemplo muestra cómo aplicar un <xref:System.Windows.Media.GuidelineSet> a una <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="51e6e-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="51e6e-104">El <xref:System.Windows.Media.DrawingGroup> clase es el único tipo de <xref:System.Windows.Media.Drawing> que tiene un <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="51e6e-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="51e6e-105">Para aplicar un <xref:System.Windows.Media.GuidelineSet> a otro tipo de <xref:System.Windows.Media.Drawing>, agréguela a una <xref:System.Windows.Media.DrawingGroup> y, a continuación, aplicar el <xref:System.Windows.Media.GuidelineSet> a su <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="51e6e-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51e6e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51e6e-106">Example</span></span>  
 <span data-ttu-id="51e6e-107">En el ejemplo siguiente se crea dos <xref:System.Windows.Media.DrawingGroup> objetos que son casi idénticos; la única diferencia es: el segundo <xref:System.Windows.Media.DrawingGroup> tiene un <xref:System.Windows.Media.GuidelineSet> y no el primero.</span><span class="sxs-lookup"><span data-stu-id="51e6e-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="51e6e-108">En la siguiente ilustración se muestra el resultado del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="51e6e-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="51e6e-109">Dado que la representación de las diferencias entre los dos <xref:System.Windows.Media.DrawingGroup> objetos es muy sutil, se aumenta el tamaño de las partes de los planos.</span><span class="sxs-lookup"><span data-stu-id="51e6e-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="51e6e-110">![DrawingGroup con y sin GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="51e6e-110">![A DrawingGroup with and without a GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="51e6e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="51e6e-111">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.GuidelineSet>  
 [<span data-ttu-id="51e6e-112">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="51e6e-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
