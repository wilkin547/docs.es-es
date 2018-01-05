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
ms.workload: dotnet
ms.openlocfilehash: 5cf689f8a7c475dbdda416297e28118d43bfdbff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Cómo: Aplicar un objeto GuidelineSet a un dibujo
Este ejemplo muestra cómo aplicar un <xref:System.Windows.Media.GuidelineSet> a una <xref:System.Windows.Media.DrawingGroup>.  
  
 El <xref:System.Windows.Media.DrawingGroup> clase es el único tipo de <xref:System.Windows.Media.Drawing> que tiene un <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> propiedad. Para aplicar un <xref:System.Windows.Media.GuidelineSet> a otro tipo de <xref:System.Windows.Media.Drawing>, agréguela a una <xref:System.Windows.Media.DrawingGroup> y, a continuación, aplicar el <xref:System.Windows.Media.GuidelineSet> a su <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea dos <xref:System.Windows.Media.DrawingGroup> objetos que son casi idénticos; la única diferencia es: el segundo <xref:System.Windows.Media.DrawingGroup> tiene un <xref:System.Windows.Media.GuidelineSet> y no el primero.  
  
 En la siguiente ilustración se muestra el resultado del ejemplo. Dado que la representación de las diferencias entre los dos <xref:System.Windows.Media.DrawingGroup> objetos es muy sutil, se aumenta el tamaño de las partes de los planos.  
  
 ![DrawingGroup con y sin GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.GuidelineSet>  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
