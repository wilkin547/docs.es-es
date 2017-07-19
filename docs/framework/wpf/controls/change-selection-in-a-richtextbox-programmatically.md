---
title: "Cambiar mediante programaci&#243;n la selecci&#243;n en un control RichTextBox | Microsoft Docs"
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
  - "cambiar las selecciones en un control RichTextBox [WPF]"
  - "cambiar las selecciones en un cuadro de texto [WPF]"
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Cambiar mediante programaci&#243;n la selecci&#243;n en un control RichTextBox
En este ejemplo se muestra cómo cambiar mediante programación la selección actual en un control <xref:System.Windows.Controls.RichTextBox>.  Esta selección es la misma que si el usuario hubiera seleccionado el contenido mediante la interfaz de usuario.  
  
## Ejemplo  
 En el código [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguiente se describe un control <xref:System.Windows.Controls.RichTextBox> con nombre con contenido simple.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## Ejemplo  
 En el código siguiente se selecciona mediante programación un texto arbitrario cuando el usuario hace clic dentro de <xref:System.Windows.Controls.RichTextBox>.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## Vea también  
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)