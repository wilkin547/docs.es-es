---
title: Procedimiento Crear y usar un control Canvas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: edef660b2da2f09e0a6edbc0a87f0d1f26eb03da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964227"
---
# <a name="how-to-create-and-use-a-canvas"></a>Procedimiento Crear y usar un control Canvas
En este ejemplo se muestra cómo crear y usar una instancia <xref:System.Windows.Controls.Canvas>de.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se coloca <xref:System.Windows.Controls.TextBlock> explícitamente dos elementos <xref:System.Windows.Controls.Canvas.SetTop%2A> mediante <xref:System.Windows.Controls.Canvas.SetLeft%2A> los métodos <xref:System.Windows.Controls.Canvas>y de. En el ejemplo también se asigna un <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Canvas>color a. `LightSteelBlue`  
  
> [!NOTE]
> Cuando use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para colocar <xref:System.Windows.Controls.TextBlock> los elementos, use las <xref:System.Windows.Controls.Canvas.Top%2A> propiedades <xref:System.Windows.Controls.Canvas.Left%2A> y.  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [Información general sobre elementos Panel](panels-overview.md)
- [Temas "Cómo..."](canvas-how-to-topics.md)
