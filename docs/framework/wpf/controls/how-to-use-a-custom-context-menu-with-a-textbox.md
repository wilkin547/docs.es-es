---
title: 'Cómo: Usar un menú contextual personalizado con un control TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: edcf6bdf381ae51a3354f9bc0b3c91d86e1f8f44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a>Cómo: Usar un menú contextual personalizado con un control TextBox
Este ejemplo muestra cómo definir e implementar un menú contextual personalizado simple para una <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se define un <xref:System.Windows.Controls.TextBox> control que incluye un menú contextual personalizado.  
  
 El menú contextual se define utilizando un <xref:System.Windows.Controls.ContextMenu> elemento.  El propio menú contextual está formada por una serie de <xref:System.Windows.Controls.MenuItem> elementos y <xref:System.Windows.Controls.Separator> elementos.  Cada <xref:System.Windows.Controls.MenuItem> elemento define un comando en el menú contextual; la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> atributo define el texto de presentación para el comando de menú y el <xref:System.Windows.Controls.MenuItem.Click> atributo especifica un método de controlador para cada elemento de menú.  El <xref:System.Windows.Controls.Separator> elemento simplemente hace que una línea de separación para representarse entre los elementos de menú anteriores y posteriores.  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el código de implementación para la definición de menú contextual anterior, así como el código que habilita y deshabilita el menú contextual.  El <xref:System.Windows.Controls.ContextMenu.Opened> eventos se usan para habilitar o deshabilitar determinados comandos según el estado actual de dinámicamente el <xref:System.Windows.Controls.TextBox>.  
  
 Para restaurar el menú contextual predeterminado, utilice la <xref:System.Windows.DependencyObject.ClearValue%2A> método para borrar el valor de la <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad.  Para deshabilitar por completo el menú contextual, establezca la <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad en una referencia nula (`Nothing` en Visual Basic).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a>Vea también  
 [Usar el corrector ortográfico con un menú contextual](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)
