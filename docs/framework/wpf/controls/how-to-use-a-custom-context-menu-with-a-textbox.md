---
title: "C&#243;mo: Usar un men&#250; contextual personalizado con un control TextBox | Microsoft Docs"
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
  - "menús contextuales, personalizadas"
  - "menús contextuales personalizados"
  - "menús, personalizadas"
  - "TextBox (control), menús de contenido personalizado"
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Usar un men&#250; contextual personalizado con un control TextBox
En este ejemplo se muestra cómo definir e implementar un menú contextual personalizado simple para un <xref:System.Windows.Controls.TextBox>.  
  
## Ejemplo  
 En el ejemplo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguiente se define un control <xref:System.Windows.Controls.TextBox> que incluye un menú contextual personalizado.  
  
 El menú contextual se define utilizando un elemento <xref:System.Windows.Controls.ContextMenu>.  El propio menú contextual está compuesto de una serie de elementos <xref:System.Windows.Controls.MenuItem> y <xref:System.Windows.Controls.Separator>.  Cada elemento <xref:System.Windows.Controls.MenuItem> define un comando en el menú contextual; el atributo <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> define el texto para mostrar del comando de menú y el atributo <xref:System.Windows.Controls.MenuItem.Click> especifica un método de controlador para cada elemento de menú.  El elemento <xref:System.Windows.Controls.Separator> simplemente hace que se represente una línea de separación entre los elementos de menú anteriores y subsiguientes.  
  
 [!code-xml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el código de implementación para la definición de menú contextual anterior, así como el código que habilita y deshabilita el menú contextual.  El evento <xref:System.Windows.Controls.ContextMenu.Opened> se utiliza para habilitar o deshabilitar dinámicamente algunos comandos según el estado actual de <xref:System.Windows.Controls.TextBox>.  
  
 Para restaurar el menú contextual predeterminado, utilice el método <xref:System.Windows.DependencyObject.ClearValue%2A> a fin de borrar el valor de la propiedad <xref:System.Windows.FrameworkElement.ContextMenu%2A>.  Para deshabilitar totalmente el menú contextual, establezca la propiedad <xref:System.Windows.FrameworkElement.ContextMenu%2A> en una referencia null \(`Nothing` en Visual Basic\).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## Vea también  
 [Usar el corrector ortográfico con un menú contextual](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)   
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)