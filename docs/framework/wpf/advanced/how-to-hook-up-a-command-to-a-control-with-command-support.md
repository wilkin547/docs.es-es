---
title: Procedimiento Enlazar un comando a un control con la compatibilidad de comandos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
ms.openlocfilehash: 4eded4812d8894b58331f26ec75c592c15e95419
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663211"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>Procedimiento Enlazar un comando a un control con la compatibilidad de comandos
En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Input.RoutedCommand> a un <xref:System.Windows.Controls.Control> que tiene compatibilidad integrada para el comando.  Para obtener un ejemplo completo que enlace comandos a varios orígenes, consulte el ejemplo [Crear un objeto RoutedCommand personalizado](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand).  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una biblioteca de comandos comunes que los programadores de aplicaciones se encuentran con regularidad.  Las clases que constituyen la biblioteca de comandos son: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> y <xref:System.Windows.Documents.EditingCommands>.  
  
 Los objetos <xref:System.Windows.Input.RoutedCommand> estáticos que componen estas clases no proporcionan la lógica del comando.  La lógica del comando está asociada al comando con un objeto <xref:System.Windows.Input.CommandBinding>.  Algunos controles tienen integrados objetos CommandBindings para algunos comandos.  Este mecanismo permite que la semántica de un comando se mantenga, mientras que la implementación real puede cambiar.  Un <xref:System.Windows.Controls.TextBox>, por ejemplo, controla el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> de manera diferente a un control diseñado para admitir imágenes, pero la idea básica del significado de pegar algo permanece intacta.  La lógica de comando no puede proporcionarla el comando, sino que en su lugar debe proporcionarla el control o la aplicación.  
  
 Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen compatibilidad integrada para algunos de los comandos de la biblioteca de comandos.  <xref:System.Windows.Controls.TextBox>, por ejemplo, admite muchos de los comandos de edición de la aplicación, como <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> y <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  El desarrollador de aplicaciones no tiene que hacer nada especial para que estos comandos funcionen con estos controles.  Si <xref:System.Windows.Controls.TextBox> es el destino del comando cuando se ejecuta el comando, controlará el comando mediante el <xref:System.Windows.Input.CommandBinding> que está integrado en el control.  
  
 A continuación se muestra cómo usar un <xref:System.Windows.Controls.MenuItem> como el origen del comando para el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, donde un <xref:System.Windows.Controls.TextBox> es el destino del comando.  Toda la lógica que define cómo realiza <xref:System.Windows.Controls.TextBox> la operación de pegado está integrada en el control <xref:System.Windows.Controls.TextBox>.  
  
 Se crea un <xref:System.Windows.Controls.MenuItem> y su propiedad <xref:System.Windows.Controls.MenuItem.Command%2A> se establece en el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> no se establece de forma explícita en el objeto <xref:System.Windows.Controls.TextBox>.  Cuando no se establece <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>, el destino para el comando es el elemento que tiene el foco de teclado.  Si el elemento que tiene el foco de teclado no admite el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> o no puede ejecutar actualmente el comando Pegar (por ejemplo, porque el Portapapeles está vacío), <xref:System.Windows.Controls.MenuItem> estará atenuado.  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)
- [Enlazar un comando a un control sin la compatibilidad de comandos](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
