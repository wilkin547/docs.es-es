---
title: Procedimiento para reducir el parpadeo de los gráficos con un búfer doble en formularios y controles
description: Obtenga información acerca de cómo reducir el parpadeo de los gráficos con el almacenamiento en búfer doble para Windows Forms y usar controles para solucionar los problemas de parpadeo asociados a las operaciones de pintura.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618134"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Procedimiento para reducir el parpadeo de los gráficos con un búfer doble en formularios y controles
El almacenamiento en doble búfer usa un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de pintura. Cuando se habilita el almacenamiento en doble búfer, todas las operaciones de pintura se representan primero en un búfer de memoria en lugar de la superficie de dibujo en la pantalla. Una vez completadas todas las operaciones de pintura, el búfer de memoria se copia directamente en la superficie de dibujo asociada a él. Dado que solo se realiza una operación de gráficos en la pantalla, se elimina el parpadeo de la imagen asociado a las operaciones de pintura complejas. Para la mayoría de las aplicaciones, el doble búfer predeterminado proporcionado por el .NET Framework proporcionará los mejores resultados. Los controles de Windows Forms estándar se almacenan en búfer doble de forma predeterminada. Puede habilitar el doble búfer predeterminado en los formularios y los controles creados de dos maneras. Puede establecer la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propiedad en o puede `true` llamar al <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer la <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> marca en `true` . Ambos métodos habilitarán el doble búfer predeterminado para su formulario o control y proporcionarán una representación de gráficos sin parpadeos. <xref:System.Windows.Forms.Control.SetStyle%2A>Solo se recomienda llamar al método para los controles personalizados para los que se ha escrito todo el código de representación.  
  
 Para escenarios de doble búfer más avanzados, como la animación o la administración avanzada de memoria, puede implementar su propia lógica de almacenamiento en búfer doble. Para obtener más información, vea [Cómo: administrar manualmente gráficos almacenados en búfer](how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Para reducir el parpadeo  
  
- Establezca la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- o -  
  
- Llame al <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer la <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> marca en `true` .  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [Gráficos de doble búfer](double-buffered-graphics.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
