---
title: "C&#243;mo: Establecer el contenido de texto de un control TextBox | Microsoft Docs"
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
  - "contenido de texto, establecer"
  - "TextBox (control), establecer contenido de texto"
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Establecer el contenido de texto de un control TextBox
En este ejemplo se muestra cómo utilizar la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> para establecer el contenido de texto inicial de un control <xref:System.Windows.Controls.TextBox>.  
  
 **Nota** Aunque la versión [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] del ejemplo podría usar las etiquetas `<TextBox.Text>` alrededor del texto del contenido <xref:System.Windows.Controls.TextBox> de cada botón, no es necesario porque <xref:System.Windows.Controls.TextBox> aplica el atributo <xref:System.Windows.Markup.ContentPropertyAttribute> a la propiedad <xref:System.Windows.Controls.TextBox.Text%2A>.  Para obtener más información, vea [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
## Ejemplo  
 [!code-xml[TextBox_MiscCode#_TextBoxSetTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## Ejemplo  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)