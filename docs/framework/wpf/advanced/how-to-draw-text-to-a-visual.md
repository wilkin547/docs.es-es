---
title: Filtrar Dibujar texto en un elemento visual
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
ms.openlocfilehash: 1ea31540ad59ab419e209e4133bcb88640cc01fe
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368923"
---
# <a name="how-to-draw-text-to-a-visual"></a>Filtrar Dibujar texto en un elemento visual
En el ejemplo siguiente se muestra cómo dibujar texto en un <xref:System.Windows.Media.DrawingVisual> mediante un <xref:System.Windows.Media.DrawingContext> objeto. Un contexto de dibujo se devuelve mediante una llamada a la <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> método de un <xref:System.Windows.Media.DrawingVisual> objeto. Puede dibujar gráficos y texto en un contexto de dibujo.  
  
 Para dibujar texto en el contexto de dibujo, use el <xref:System.Windows.Media.DrawingContext.DrawText%2A> método de un <xref:System.Windows.Media.DrawingContext> objeto. Cuando haya terminado de dibujar el contenido en el contexto de dibujo, llame a la <xref:System.Windows.Media.DrawingContext.Close%2A> para cerrar el contexto de dibujo y conservar el contenido.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).
