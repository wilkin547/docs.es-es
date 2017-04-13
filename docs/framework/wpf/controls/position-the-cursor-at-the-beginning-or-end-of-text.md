---
title: "C&#243;mo: Colocar el cursor al principio o al final del texto de un control | Microsoft Docs"
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
  - "colocar el cursor"
  - "TextBox (control), colocar el cursor"
  - "cursor, posición"
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Colocar el cursor al principio o al final del texto de un control
Este ejemplo muestra cómo colocar el cursor al principio o al final del contenido de texto de un <xref:System.Windows.Controls.TextBox> control.  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código describe una <xref:System.Windows.Controls.TextBox> controlar y le asigna un nombre.  
  
 [!code-xml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>Ejemplo  
 Para colocar el cursor al principio del contenido de un <xref:System.Windows.Controls.TextBox> control, llame a la <xref:System.Windows.Controls.TextBox.Select%2A> (método) y especifique el inicio de la selección de posición de 0 y una selección de longitud 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>Ejemplo  
 Para colocar el cursor al final del contenido de un <xref:System.Windows.Controls.TextBox> control, llame a la <xref:System.Windows.Controls.TextBox.Select%2A> método y especificar la posición de inicio de la selección igual a la longitud del texto del contenido y una selección de longitud 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general del control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)