---
title: "C&#243;mo: Administrar manualmente gr&#225;ficos almacenados en b&#250;fer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BufferedGraphicsContext (clase)"
  - "parpadeo, reducir mediante la administración manual de gráficos"
  - "gráficos, administrar almacenados en búfer"
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Administrar manualmente gr&#225;ficos almacenados en b&#250;fer
En aquellos escenarios de doble búfer más avanzados, se pueden utilizar las clases de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para implementar su propia lógica de búfer doble.  La clase responsable de asignar y administrar búferes de gráficos individuales es la clase <xref:System.Drawing.BufferedGraphicsContext>.  Cada aplicación tiene su propio <xref:System.Drawing.BufferedGraphicsContext> predeterminado que administra todos los búferes dobles predeterminados para dicha aplicación.  Puede recuperar una referencia a esta instancia mediante la llamada a la propiedad <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### Para obtener una referencia a la clase BufferedGraphicsContext predeterminada  
  
-   Establezca la propiedad <xref:System.Drawing.BufferedGraphicsManager.Current%2A>, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  No tiene que llamar al método `Dispose` en la referencia <xref:System.Drawing.BufferedGraphicsContext> que recibe de la clase <xref:System.Drawing.BufferedGraphicsManager>.  La clase <xref:System.Drawing.BufferedGraphicsManager> controla la asignación y la distribución de memoria para las instancias de <xref:System.Drawing.BufferedGraphicsContext> predeterminadas.  
  
     En aquellas aplicaciones que utilizan gráficos de forma intensiva, a veces se puede mejorar el rendimiento utilizando una clase <xref:System.Drawing.BufferedGraphicsContext> dedicada en lugar de <xref:System.Drawing.BufferedGraphicsContext> proporcionada por <xref:System.Drawing.BufferedGraphicsManager>.  Este sistema permite crear y administrar búferes de gráficos individualmente, sin causar la sobrecarga de rendimiento de administrar el resto de gráficos almacenados en búfer asociados con la aplicación, aunque la memoria consumida por la aplicación será mayor.  
  
### Para crear una clase BufferedGraphicsContext dedicada  
  
-   Declare y cree una nueva instancia de la clase <xref:System.Drawing.BufferedGraphicsContext>, como se muestra en el ejemplo de código siguiente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## Vea también  
 <xref:System.Drawing.BufferedGraphicsContext>   
 [Gráficos de doble búfer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [Cómo: Representar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)