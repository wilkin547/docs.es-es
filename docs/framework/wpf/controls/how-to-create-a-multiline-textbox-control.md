---
title: "C&#243;mo: Crear un control TextBox multil&#237;nea | Microsoft Docs"
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
  - "TextBox (control), varias líneas de texto"
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Crear un control TextBox multil&#237;nea
En este ejemplo se muestra cómo utilizar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un control <xref:System.Windows.Controls.TextBox> que se expande automáticamente para alojar varias líneas de texto.  
  
## Ejemplo  
 Al establecer el atributo <xref:System.Windows.Controls.TextBox.TextWrapping%2A> en **Wrap**, el texto se ajusta para continuar en una nueva línea cuando se alcanza el borde del control <xref:System.Windows.Controls.TextBox>, lo que expande automáticamente el control <xref:System.Windows.Controls.TextBox> a fin de incluir espacio para una nueva línea, si es necesario.  
  
 Establecer el atributo <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> en **true** hace que se inserte una nueva línea cuando se presiona la tecla ENTRAR, con lo que <xref:System.Windows.Controls.TextBox> se expande automáticamente una vez más a fin de incluir espacio para una nueva línea, si es necesario.  
  
 El atributo <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> agrega una barra de desplazamiento a <xref:System.Windows.Controls.TextBox>, a fin de que sea posible recorrer el contenido de <xref:System.Windows.Controls.TextBox> si <xref:System.Windows.Controls.TextBox> se expande más allá del tamaño del marco o de la ventana que lo enmarca.  
  
 [!code-xml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## Vea también  
 <xref:System.Windows.TextWrapping>   
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)