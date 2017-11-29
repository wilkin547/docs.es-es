---
title: "Cómo: Dibujar texto en un elemento visual"
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
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 735a84a034587b1433403a45edc7c2f459340273
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a>Cómo: Dibujar texto en un elemento visual
En el ejemplo siguiente se muestra cómo dibujar texto en un <xref:System.Windows.Media.DrawingVisual> mediante un <xref:System.Windows.Media.DrawingContext> objeto. Se devuelve un contexto de dibujo mediante una llamada a la <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> método de una <xref:System.Windows.Media.DrawingVisual> objeto. Puede dibujar gráficos y texto en un contexto de dibujo.  
  
 Para dibujar texto en el contexto de dibujo, utilice la <xref:System.Windows.Media.DrawingContext.DrawText%2A> método de una <xref:System.Windows.Media.DrawingContext> objeto. Cuando haya terminado de dibujar contenido en el contexto de dibujo, llame a la <xref:System.Windows.Media.DrawingContext.Close%2A> método para cerrar el contexto de dibujo y conservar el contenido.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).
