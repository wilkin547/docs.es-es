---
title: "C&#243;mo: Reducir el parpadeo de los gr&#225;ficos con un b&#250;fer doble en formularios y controles | Microsoft Docs"
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
  - "DoubleBuffered (propiedad)"
  - "parpadeo, reducir en formularios Windows Forms"
  - "gráficos, reducir parpadeo con doble búfer"
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Reducir el parpadeo de los gr&#225;ficos con un b&#250;fer doble en formularios y controles
El búfer doble utiliza un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de representación.  Cuando se habilita el doble búfer, todas las operaciones de representación se representan en primer lugar en un búfer de memoria en lugar de en la pantalla.  Después de finalizar todas las operaciones de representación, el búfer de memoria se copia directamente en la superficie de representación asociada.  Puesto que solo se realiza una operación de gráficos en la pantalla, se elimina el parpadeo de la imagen asociado a operaciones complejas de representación. En la mayoría de las aplicaciones, el almacenamiento en búfer doble predeterminado proporcionado por [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporcionará los mejores resultados.  De forma predeterminada, los controles estándar de los formularios Windows Forms tienen un búfer doble.  Se puede habilitar el búfer doble predeterminado en los formularios y en los controles creados de dos maneras.  O bien se puede establecer la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true` o bien llamar al método <xref:System.Windows.Forms.Control.SetStyle%2A> para que establezca el marcador <xref:System.Windows.Forms.ControlStyles> en `true`.  Ambos métodos habilitarán el búfer doble predeterminado en el formulario o control y proporcionará una representación de los gráficos sin parpadeo.  Sólo se recomienda llamar al método <xref:System.Windows.Forms.Control.SetStyle%2A> en los controles personalizados para los que se ha escrito todo el código de representación.  
  
 En aquellos escenarios de doble búfer más avanzados, como animación o administración de memoria avanzada, se puede implementar la lógica de doble búfer propia.  Para obtener más información, vea [Cómo: Administrar manualmente gráficos almacenados en búfer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### Para reducir el parpadeo  
  
-   Establezca la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \-O bien\-  
  
-   Llame al método <xref:System.Windows.Forms.Control.SetStyle%2A> para establecer el marcador <xref:System.Windows.Forms.ControlStyles> en `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## Vea también  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>   
 <xref:System.Windows.Forms.Control.SetStyle%2A>   
 [Gráficos de doble búfer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)