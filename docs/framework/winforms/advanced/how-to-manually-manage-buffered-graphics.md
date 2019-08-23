---
title: Procedimiento para administrar manualmente gráficos almacenados en búfer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968597"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Procedimiento para administrar manualmente gráficos almacenados en búfer
Para escenarios de doble búfer más avanzados, puede usar las clases .NET Framework para implementar su propia lógica de doble búfer. La clase responsable de la asignación y administración de búferes de gráficos <xref:System.Drawing.BufferedGraphicsContext> individuales es la clase. Cada aplicación tiene su propio valor <xref:System.Drawing.BufferedGraphicsContext> predeterminado que administra todo el búfer doble predeterminado para esa aplicación. Puede recuperar una referencia a esta instancia llamando <xref:System.Drawing.BufferedGraphicsManager.Current%2A>a.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Para obtener una referencia al BufferedGraphicsContext predeterminado  
  
- Establezca la <xref:System.Drawing.BufferedGraphicsManager.Current%2A> propiedad, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > No es necesario llamar al `Dispose` método en la <xref:System.Drawing.BufferedGraphicsContext> referencia que se recibe de la <xref:System.Drawing.BufferedGraphicsManager> clase. Controla toda la asignación de memoria y la distribución de las instancias predeterminadas <xref:System.Drawing.BufferedGraphicsContext>. <xref:System.Drawing.BufferedGraphicsManager>  
  
     En el <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsContext> casodelasaplicacionesconunusointensivodegráficoscomolaanimación,enocasionespuedemejorarelrendimientomedianteundedicadoenlugardelos<xref:System.Drawing.BufferedGraphicsManager>proporcionados por. Esto le permite crear y administrar búferes de gráficos individualmente, sin incurrir en la sobrecarga de rendimiento que supone administrar todos los demás gráficos almacenados en búfer asociados a la aplicación, aunque la memoria consumida por la aplicación será mayor.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Para crear un BufferedGraphicsContext dedicado  
  
- Declare y cree una instancia nueva de <xref:System.Drawing.BufferedGraphicsContext> la clase, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.BufferedGraphicsContext>
- [Gráficos de doble búfer](double-buffered-graphics.md)
- [Cómo: Representar manualmente gráficos almacenados en búfer](how-to-manually-render-buffered-graphics.md)
