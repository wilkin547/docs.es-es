---
title: "C&#243;mo: Cambiar la propiedad TextWrapping mediante programaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "documentos, cambiar la propiedad TextWrapping mediante programación"
  - "TextWrapping (propiedad), cambiar mediante programación"
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Cambiar la propiedad TextWrapping mediante programaci&#243;n
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo cambiar el valor de la propiedad <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> mediante programación.  
  
 Se colocan tres elementos <xref:System.Windows.Controls.Button> en un elemento <xref:System.Windows.Controls.StackPanel> de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Cada evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> de un control <xref:System.Windows.Controls.Button> se corresponde con un controlador de eventos en el código.  Los controladores de eventos utilizan el mismo nombre que el valor de <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> que aplicarán a `txt2` cuando se haga clic en el botón.  Asimismo, se actualiza el texto de `txt1` \(un objeto <xref:System.Windows.Controls.TextBlock> que no se muestra en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\) para reflejar el cambio de la propiedad.  
  
 [!code-xml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>   
 <xref:System.Windows.TextWrapping>