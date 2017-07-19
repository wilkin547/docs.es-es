---
title: "Informaci&#243;n general sobre TextBlock | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles de TextBlock"
  - "TextBlock (control)"
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Informaci&#243;n general sobre TextBlock
El <xref:System.Windows.Controls.TextBlock> control proporciona compatibilidad con texto flexible [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones. El elemento se destina principalmente a basic [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] escenarios que no requieren más de un párrafo de texto. Admite un número de propiedades que permiten un control preciso de presentación, como <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, y <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>. Contenido de texto se puede agregar utilizando el <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad. Cuando se utiliza en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], contenido entre la apertura y la etiqueta de cierre se agrega implícitamente como el texto del elemento.  
  
 Un <xref:System.Windows.Controls.TextBlock> elemento puede implementarse fácilmente mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[TextBlockSnip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 De forma similar, el uso de la <xref:System.Windows.Controls.TextBlock> elemento de código es relativamente sencilla.  
  
 [!code-csharp[TextBlockSnip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Label>