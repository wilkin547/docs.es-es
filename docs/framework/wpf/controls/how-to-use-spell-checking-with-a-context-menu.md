---
title: "Cómo: Usar el corrector ortográfico con un menú contextual"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a85426dc526e1e8560f494bcde5247fc394f7bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>Cómo: Usar el corrector ortográfico con un menú contextual
De forma predeterminada, cuando se habilita el corrector ortográfico en un control de edición como <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>, obtendrá las opciones de revisión ortográfica en el menú contextual. Por ejemplo, cuando los usuarios haga clic en una palabra mal escrita, obtener un conjunto de sugerencias de ortografía o la opción de **omitir todas**. Sin embargo, cuando se reemplaza con su propio menú contextual personalizado en el menú contextual de predeterminado, esta funcionalidad se pierde y necesita escribir código para volver a habilitar la característica de corrector ortográfico en el menú contextual. En el ejemplo siguiente se muestra cómo habilitarla en un <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo se muestra la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que crea un <xref:System.Windows.Controls.TextBox> con algunos eventos que se usan para implementar el menú contextual.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el código que implementa el menú contextual.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 El código utilizado para hacer esto con un <xref:System.Windows.Controls.RichTextBox> es similar. La diferencia principal radica en el parámetro pasado a la `GetSpellingError` método. Para una <xref:System.Windows.Controls.TextBox>, pase el índice de entero de la posición del símbolo de intercalación:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Para una <xref:System.Windows.Controls.RichTextBox>, pasar la <xref:System.Windows.Documents.TextPointer> que especifica la posición del símbolo de intercalación:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)  
 [Habilitar el corrector ortográfico en un control de edición de texto](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [Usar un menú contextual personalizado con un control TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
