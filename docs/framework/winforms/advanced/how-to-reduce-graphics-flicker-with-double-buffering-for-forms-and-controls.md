---
title: "Cómo: Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc782ba262527a319cbb05cc6d36ca568afc55c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Cómo: Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles
El almacenamiento en doble búfer usa un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de pintura. Cuando se habilita el almacenamiento en doble búfer, todas las operaciones de pintura se representan primero en un búfer de memoria en lugar de la superficie de dibujo en la pantalla. Una vez completadas todas las operaciones de pintura, el búfer de memoria se copia directamente en la superficie de dibujo asociada a él. Dado que las operaciones de solo gráficos se realiza en la pantalla, se elimina el parpadeo de las imágenes asociadas a operaciones de dibujo complejas. Para la mayoría de las aplicaciones, el búfer doble predeterminado proporcionado por el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporcionará los mejores resultados. Controles de formularios Windows Forms estándar tienen dobles búfer de forma predeterminada. Puede habilitar de forma predeterminada el doble búfer en los formularios y controles creados de dos maneras. Puede establecer la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propiedad `true`, o puede llamar a la <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer el <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> indicador en `true`. Ambos métodos habilitará de forma predeterminada un búfer doble en el formulario o control y proporcionar la representación de gráficos sin parpadeo. Llamar a la <xref:System.Windows.Forms.Control.SetStyle%2A> método solo se recomienda para controles personalizados para el que ha escrito el código de representación.  
  
 Para escenarios almacenamiento en búfer dobles y más avanzados, como animación o administración de memoria avanzados, puede implementar su propia lógica de almacenamiento en búfer doble. Para obtener más información, consulte [Cómo: Manually Manage Buffered Graphics](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Para reducir el parpadeo  
  
-   Establezca la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- o -  
  
-   Llame a la <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer el <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> indicador en `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>  
 <xref:System.Windows.Forms.Control.SetStyle%2A>  
 [Gráficos de doble búfer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
