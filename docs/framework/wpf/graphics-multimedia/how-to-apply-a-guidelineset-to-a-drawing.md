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
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Procedimiento Aplicar un objeto GuidelineSet a un dibujo
En este ejemplo se muestra cómo aplicar un <xref:System.Windows.Media.GuidelineSet> a un <xref:System.Windows.Media.DrawingGroup>.  
  
 El <xref:System.Windows.Media.DrawingGroup> clase es el único tipo de <xref:System.Windows.Media.Drawing> que tiene un <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> propiedad. Para aplicar un <xref:System.Windows.Media.GuidelineSet> a otro tipo de <xref:System.Windows.Media.Drawing>, agréguela a un <xref:System.Windows.Media.DrawingGroup> y, a continuación, aplicar el <xref:System.Windows.Media.GuidelineSet> a su <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crean dos <xref:System.Windows.Media.DrawingGroup> objetos que son casi idénticos; la única diferencia es: el segundo <xref:System.Windows.Media.DrawingGroup> tiene un <xref:System.Windows.Media.GuidelineSet> y no el primero.  
  
 En la siguiente ilustración se muestra el resultado del ejemplo. Dado que la representación de las diferencias entre los dos <xref:System.Windows.Media.DrawingGroup> objetos es muy sutil, se amplían partes de los dibujos.  
  
 ![DrawingGroup con y sin GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
