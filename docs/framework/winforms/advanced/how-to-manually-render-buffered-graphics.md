---
title: Filtrar Representar manualmente gráficos almacenados en búfer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: f9763620d5fe56a0720d5d5f4ad53ec2ef18531c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705810"
---
# <a name="how-to-manually-render-buffered-graphics"></a>Filtrar Representar manualmente gráficos almacenados en búfer
Si administra sus propios gráficos almacenados en búfer, deberá poder crear y representar búferes de gráficos. Puede crear instancias de la clase <xref:System.Drawing.BufferedGraphics> que está asociada con las superficies de dibujo en pantalla mediante llamadas al método <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>. Este método crea una instancia <xref:System.Drawing.BufferedGraphics> que está asociada a una superficie de representación determinada, como un formulario o un control. Después de crear una instancia de <xref:System.Drawing.BufferedGraphics>, puede dibujar gráficos en el búfer que se representan mediante la propiedad <xref:System.Drawing.BufferedGraphics.Graphics%2A>. Después de haber realizado todas las operaciones de gráficos, puede copiar el contenido del búfer en la pantalla llamando al método <xref:System.Drawing.BufferedGraphics.Render%2A>.  
  
> [!NOTE]
>  Si realiza su propia representación, aumentará el consumo de memoria, aunque este aumento puede ser ligero.  
  
### <a name="to-manually-display-buffered-graphics"></a>Para mostrar manualmente los gráficos almacenados en búfer  
  
1.  Obtenga una referencia a una instancia de la clase <xref:System.Drawing.BufferedGraphicsContext>. Para obtener más información, vea [Cómo: Administrar manualmente gráficos almacenados en búfer](how-to-manually-manage-buffered-graphics.md).  
  
2.  Cree una instancia de la clase <xref:System.Drawing.BufferedGraphics> llamando al método <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>, tal y como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3.  Dibuje los gráficos en el búfer de gráficos estableciendo la propiedad <xref:System.Drawing.BufferedGraphics.Graphics%2A>. Por ejemplo:  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4.  Cuando haya completado todas las operaciones de dibujo en el búfer de gráficos, llame al método <xref:System.Drawing.BufferedGraphics.Render%2A> para representar el búfer, bien en la superficie de dibujo asociada con dicho búfer, o en una superficie de dibujo que especifique, tal y como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5.  Cuando haya terminado de representar los gráficos, llame al método `Dispose` en la instancia <xref:System.Drawing.BufferedGraphics> para liberar recursos del sistema.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphics>
- [Gráficos de doble búfer](double-buffered-graphics.md)
- [Cómo: Administrar manualmente gráficos almacenados en búfer](how-to-manually-manage-buffered-graphics.md)
