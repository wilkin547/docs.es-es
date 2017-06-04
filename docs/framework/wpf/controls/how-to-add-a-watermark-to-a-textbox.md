---
title: "C&#243;mo: Agregar una marca de agua a un TextBox | Microsoft Docs"
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
  - "mejorar la facilidad de uso de un control TextBox mediante una imagen de fondo [WPF]"
  - "mostrar una imagen de fondo dentro de un cuadro de texto durante la entrada del usuario [WPF]"
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Agregar una marca de agua a un TextBox
En el ejemplo siguiente se muestra cómo facilitar el uso de un control <xref:System.Windows.Controls.TextBox> mostrando una imagen de fondo explicativa dentro de <xref:System.Windows.Controls.TextBox> hasta que el usuario escribe texto, momento en que se quita la imagen.  Además, la imagen de fondo se restaura si el usuario quita los datos proporcionados.  Vea la ilustración siguiente.  
  
 ![TextBox con una imagen de fondo](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing\_TextBox\_using\_background\_image")  
  
> [!NOTE]
>  La razón de utilizar una imagen de fondo en este ejemplo, en lugar de limitarnos a manipular la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> de <xref:System.Windows.Controls.TextBox>, es que una imagen de fondo no interfiere con el enlace de datos.  
  
## Ejemplo  
 [!code-xml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)