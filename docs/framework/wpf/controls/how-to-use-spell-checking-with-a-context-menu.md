---
title: "C&#243;mo: Usar el corrector ortogr&#225;fico con un men&#250; contextual | Microsoft Docs"
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
  - "habilitar la revisión ortográfica en un cuadro de texto [WPF]"
  - "volver a habilitar la revisión ortográfica en un cuadro de texto [WPF]"
  - "corrector ortográfico con un menú contextual [WPF]"
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Usar el corrector ortogr&#225;fico con un men&#250; contextual
De manera predeterminada, al habilitar la revisión ortográfica en un control de edición como <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>, se obtienen las opciones de revisión ortográfica en el menú contextual.  Por ejemplo, cuando los usuarios hacen clic con el botón secundario en una palabra incorrecta, obtienen un conjunto de sugerencias ortográficas, o la opción a **Omitir todas**.  Sin embargo, si invalida el menú contextual predeterminado con su propio menú contextual personalizado, se pierde esta funcionalidad y es preciso escribir código para volver a habilitar la característica de revisión ortográfica en el menú contextual.  En el ejemplo siguiente se muestra cómo habilitarla en un control <xref:System.Windows.Controls.TextBox>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que crea un control <xref:System.Windows.Controls.TextBox> con algunos eventos que se emplean para implementar el menú contextual.  
  
 [!code-xml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el código que implementa el menú contextual.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 El código utilizado para ello con un control <xref:System.Windows.Controls.RichTextBox> es similar.  La diferencia principal reside en el parámetro que se pasa al método `GetSpellingError`.  Para <xref:System.Windows.Controls.TextBox>, se pasa el índice de tipo entero correspondiente a la posición del símbolo de intercalación:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Para <xref:System.Windows.Controls.RichTextBox>, se pasa el objeto <xref:System.Windows.Documents.TextPointer> que especifica la posición del símbolo de intercalación:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Habilitar el corrector ortográfico en un control de edición de texto](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)   
 [Usar un menú contextual personalizado con un control TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)