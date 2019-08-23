---
title: Procedimiento Enumerar el contenido de un dibujo de un objeto visual
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930069"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>Procedimiento Enumerar el contenido de un dibujo de un objeto visual
El <xref:System.Windows.Media.Drawing> objeto proporciona un modelo de objetos para enumerar el contenido de <xref:System.Windows.Media.Visual>un objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> usa el método para <xref:System.Windows.Media.DrawingGroup> recuperar el valor <xref:System.Windows.Media.Visual> de un y enumerarlo.  
  
> [!NOTE]
> Cuando se enumera el contenido del objeto visual, se recuperan <xref:System.Windows.Media.Drawing> los objetos y no la representación subyacente de los datos de representación como una lista de instrucciones de gráficos vectoriales. Para más información, consulte [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
