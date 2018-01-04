---
title: "Cómo: Enlazar un comando a un control con la compatibilidad de comandos"
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
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b190868b8718442966a22d7be14d976ec47f53b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>Cómo: Enlazar un comando a un control con la compatibilidad de comandos
En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Input.RoutedCommand> a una <xref:System.Windows.Controls.Control> que tiene compatibilidad integrada para el comando.  Para obtener un ejemplo completo que enlace comandos a varios orígenes, consulte el ejemplo [Crear un objeto RoutedCommand personalizado](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una biblioteca de comandos comunes que los programadores de aplicaciones se encuentran con regularidad.  Las clases que constituyen la biblioteca de comandos son: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, y <xref:System.Windows.Documents.EditingCommands>.  
  
 El método estático <xref:System.Windows.Input.RoutedCommand> objetos que componen estas clases no proporcionan la lógica de comandos.  La lógica para el comando está asociada con el comando con un <xref:System.Windows.Input.CommandBinding>.  Algunos controles tienen integrados objetos CommandBindings para algunos comandos.  Este mecanismo permite que la semántica de un comando se mantenga, mientras que la implementación real puede cambiar.  A <xref:System.Windows.Controls.TextBox>, por ejemplo, controla el <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando de manera diferente que un control diseñado para admitir imágenes, pero la idea básica de lo que significa para pegar algo sigue siendo el mismo.  La lógica de comando no puede proporcionarla el comando, sino que en su lugar debe proporcionarla el control o la aplicación.  
  
 Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen compatibilidad integrada para algunos de los comandos de la biblioteca de comandos.  <xref:System.Windows.Controls.TextBox>, por ejemplo, admite muchos de los comandos de edición de la aplicación, como <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, y <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  El desarrollador de aplicaciones no tiene que hacer nada especial para que estos comandos funcionen con estos controles.  Si el <xref:System.Windows.Controls.TextBox> es el destino del comando cuando se ejecuta el comando, controlará el comando mediante el <xref:System.Windows.Input.CommandBinding> que está integrado en el control.  
  
 La siguiente muestra cómo utilizar un <xref:System.Windows.Controls.MenuItem> como el origen del comando para el <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando, donde un <xref:System.Windows.Controls.TextBox> es el destino del comando.  Toda la lógica que define cómo el <xref:System.Windows.Controls.TextBox> realiza la operación de pegado está integrada en el <xref:System.Windows.Controls.TextBox> control.  
  
 A <xref:System.Windows.Controls.MenuItem> se crea y es <xref:System.Windows.Controls.MenuItem.Command%2A> propiedad está establecida en el <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando.  El <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> no se establece explícitamente en el <xref:System.Windows.Controls.TextBox> objeto.  Cuando el <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> no se establece, el destino para el comando es el elemento que tiene el foco de teclado.  Si el elemento que tiene el foco de teclado no admite la <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando o actualmente no se puede ejecutar el comando Pegar (el Portapapeles está vacío, por ejemplo), a continuación, el <xref:System.Windows.Controls.MenuItem> podría mostrarse en gris.  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Enlazar un comando a un control sin la compatibilidad de comandos](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
