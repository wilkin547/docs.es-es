---
title: "Cómo: Administrar manualmente gráficos almacenados en búfer"
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
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678b9ad5e8f9b40f927a35e98973cabc831c5cf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Cómo: Administrar manualmente gráficos almacenados en búfer
Para escenarios más avanzados de almacenamiento en búfer dobles, puede usar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] las clases para implementar su propia lógica de almacenamiento en búfer doble. La clase responsable de asignar y administrar los búferes de gráficos individuales es la <xref:System.Drawing.BufferedGraphicsContext> clase. Cada aplicación tiene su propio valor predeterminado <xref:System.Drawing.BufferedGraphicsContext> que administra todos de manera predeterminada el doble búfer para esa aplicación. Puede recuperar una referencia a esta instancia mediante una llamada a la <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Para obtener una referencia a la clase BufferedGraphicsContext predeterminada  
  
-   Establecer el <xref:System.Drawing.BufferedGraphicsManager.Current%2A> propiedad, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  No es necesario llamar a la `Dispose` método en el <xref:System.Drawing.BufferedGraphicsContext> referencia que recibe la <xref:System.Drawing.BufferedGraphicsManager> clase. El <xref:System.Drawing.BufferedGraphicsManager> se encarga de toda la asignación de memoria de distribución predeterminada <xref:System.Drawing.BufferedGraphicsContext> instancias.  
  
     Para las aplicaciones gráficamente intensivas como las animaciones, a veces puede mejorar el rendimiento mediante el uso de una dedicado <xref:System.Drawing.BufferedGraphicsContext> en lugar de la <xref:System.Drawing.BufferedGraphicsContext> proporcionada por el <xref:System.Drawing.BufferedGraphicsManager>. Esto le permite crear y administrar búferes de gráficos individualmente, sin incurrir en la sobrecarga de rendimiento de la administración de todos los otros gráficos almacenados en búfer asociados a la aplicación, aunque la memoria consumida por la aplicación será mayor.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Para crear una clase BufferedGraphicsContext dedicada  
  
-   Declarar y crear una nueva instancia de la <xref:System.Drawing.BufferedGraphicsContext> de la clase, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [Gráficos de doble búfer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [Representar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
