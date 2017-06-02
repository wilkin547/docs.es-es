---
title: "C&#243;mo: Extraer el contenido de texto de un control RichTextBox | Microsoft Docs"
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
  - "contenido, extraer"
  - "extraer contenido de texto"
  - "RichTextBox (control), extraer contenido de texto"
  - "contenido de texto, extraer"
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Extraer el contenido de texto de un control RichTextBox
En este ejemplo se muestra cómo extraer el contenido de un control <xref:System.Windows.Controls.RichTextBox> como texto sin formato.  
  
## Ejemplo  
 En el código [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguiente se describe un control <xref:System.Windows.Controls.RichTextBox> con nombre con contenido simple.  
  
 [!code-xml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## Ejemplo  
 En el código siguiente se implementa un método que toma <xref:System.Windows.Controls.RichTextBox> como un argumento y devuelve una cadena que representa el contenido de texto sin formato de <xref:System.Windows.Controls.RichTextBox>.  
  
 El método crea un nuevo objeto <xref:System.Windows.Documents.TextRange> a partir del contenido de <xref:System.Windows.Controls.RichTextBox>, utilizando las propiedades <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> y <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> para indicar el intervalo de contenido que se va a extraer.  Las propiedades <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> y <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> devuelven un objeto<xref:System.Windows.Documents.TextPointer> cada una, y están accesibles en el objeto FlowDocument subyacente que representa el contenido de <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange> proporciona una propiedad Text, que devuelve las partes de texto sin formato de <xref:System.Windows.Documents.TextRange> como una cadena.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## Vea también  
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)