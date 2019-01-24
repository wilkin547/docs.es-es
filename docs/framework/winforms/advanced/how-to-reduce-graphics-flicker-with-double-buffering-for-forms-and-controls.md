---
title: Procedimiento Reducir el parpadeo de gráficos con un búfer doble en formularios y controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: 96bdaa8882b5f33c68d2a87dd28163c1acd606bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663588"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Procedimiento Reducir el parpadeo de gráficos con un búfer doble en formularios y controles
El almacenamiento en doble búfer usa un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de pintura. Cuando se habilita el almacenamiento en doble búfer, todas las operaciones de pintura se representan primero en un búfer de memoria en lugar de la superficie de dibujo en la pantalla. Una vez completadas todas las operaciones de pintura, el búfer de memoria se copia directamente en la superficie de dibujo asociada a él. Dado que se realiza solo una única operación gráfica en la pantalla, se elimina, el parpadeo de las imágenes asociadas a operaciones de pintura complejas. Para la mayoría de las aplicaciones, el búfer doble predeterminado proporcionado por el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporcionará los mejores resultados. Controles estándar de Windows Forms tienen dobles búfer de forma predeterminada. Se puede habilitar de forma predeterminada en doble búfer en los formularios y controles creados de dos maneras. Puede establecer el <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propiedad `true`, o bien puede llamar el <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer el <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> marca a `true`. Ambos métodos habilitará de forma predeterminada un búfer doble en formularios y controles y proporcionar la representación de gráficos sin parpadeo. Una llamada a la <xref:System.Windows.Forms.Control.SetStyle%2A> método solo se recomienda para los controles personalizados para el que ha escrito todo el código de representación.  
  
 Para más avanzados escenarios de almacenamiento en búfer doble, como animación o administración avanzada de memoria, puede implementar su propia lógica de almacenamiento en búfer doble. Para obtener más información, vea [Cómo: Administrar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Para reducir el parpadeo  
  
-   Establezca la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- o -  
  
-   Llame a la <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer el <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> marca `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [Gráficos de doble búfer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)
- [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
