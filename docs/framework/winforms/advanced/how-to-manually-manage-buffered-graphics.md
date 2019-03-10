---
title: Filtrar Administrar manualmente gráficos almacenados en búfer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 013118ea15184ee4dfbbcd5dcaff054a2cf6a9ba
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702937"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Filtrar Administrar manualmente gráficos almacenados en búfer
Para escenarios más avanzados de almacenamiento en búfer doble, puede usar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] clases para implementar su propia lógica de almacenamiento en búfer doble. La clase responsable de asignar y administrar búferes de gráficos individuales es el <xref:System.Drawing.BufferedGraphicsContext> clase. Cada aplicación tiene su propio valor predeterminado <xref:System.Drawing.BufferedGraphicsContext> que administra todo el doble búfer predeterminado para esa aplicación. Puede recuperar una referencia a esta instancia mediante una llamada a la <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Para obtener una referencia a la clase BufferedGraphicsContext predeterminada  
  
-   Establecer el <xref:System.Drawing.BufferedGraphicsManager.Current%2A> propiedad, como se muestra en el siguiente ejemplo de código.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  No es necesario llamar a la `Dispose` método en el <xref:System.Drawing.BufferedGraphicsContext> referencia procedente de la <xref:System.Drawing.BufferedGraphicsManager> clase. El <xref:System.Drawing.BufferedGraphicsManager> controla toda la asignación de memoria y la distribución predeterminada <xref:System.Drawing.BufferedGraphicsContext> instancias.  
  
     Para aplicaciones intensivas gráficamente como animación, en ocasiones puede mejorar el rendimiento mediante el uso de una dedicado <xref:System.Drawing.BufferedGraphicsContext> en lugar de la <xref:System.Drawing.BufferedGraphicsContext> proporcionada por el <xref:System.Drawing.BufferedGraphicsManager>. Esto le permite crear y administrar búferes de gráficos individualmente, sin incurrir en la sobrecarga de rendimiento de la administración de todas los otros gráficos almacenados en búfer asociados con la aplicación, aunque la memoria consumida por la aplicación será mayor.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Para crear una clase BufferedGraphicsContext dedicada  
  
-   Declare y cree una nueva instancia de la <xref:System.Drawing.BufferedGraphicsContext> clase, como se muestra en el siguiente ejemplo de código.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.BufferedGraphicsContext>
- [Gráficos de doble búfer](double-buffered-graphics.md)
- [Cómo: Representar manualmente gráficos almacenados en búfer](how-to-manually-render-buffered-graphics.md)
