---
title: 'Cómo: Dibujar texto en un elemento visual'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094558"
---
# <a name="how-to-draw-text-to-a-visual"></a>Cómo: Dibujar texto en un elemento visual
En el ejemplo siguiente se muestra cómo dibujar texto en un <xref:System.Windows.Media.DrawingVisual> mediante un objeto <xref:System.Windows.Media.DrawingContext>. Un contexto de dibujo se devuelve mediante una llamada al método <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> de un objeto <xref:System.Windows.Media.DrawingVisual>. Puede dibujar gráficos y texto en un contexto de dibujo.  
  
 Para dibujar texto en el contexto del dibujo, use el método <xref:System.Windows.Media.DrawingContext.DrawText%2A> de un objeto <xref:System.Windows.Media.DrawingContext>. Cuando haya terminado de dibujar el contenido en el contexto del dibujo, llame al método <xref:System.Windows.Media.DrawingContext.Close%2A> para cerrar el contexto del dibujo y conservar el contenido.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).
