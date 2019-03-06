---
title: Procedimiento Crear y utilizar un control Canvas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: 13ed32195621350284530da78544e026ed341658
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360386"
---
# <a name="how-to-create-and-use-a-canvas"></a>Filtrar Crear y utilizar un control Canvas
En este ejemplo se muestra cómo crear y usar una instancia de <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente coloca explícitamente dos <xref:System.Windows.Controls.TextBlock> elementos mediante el uso de la <xref:System.Windows.Controls.Canvas.SetTop%2A> y <xref:System.Windows.Controls.Canvas.SetLeft%2A> métodos de <xref:System.Windows.Controls.Canvas>. El ejemplo también se asigna un <xref:System.Windows.Controls.Control.Background%2A> color de `LightSteelBlue` a la <xref:System.Windows.Controls.Canvas>.  
  
> [!NOTE]
>  Cuando usas [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] a posición <xref:System.Windows.Controls.TextBlock> elementos, utilice el <xref:System.Windows.Controls.Canvas.Top%2A> y <xref:System.Windows.Controls.Canvas.Left%2A> propiedades.  
  
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
