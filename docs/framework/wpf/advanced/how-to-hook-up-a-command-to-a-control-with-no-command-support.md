---
title: Procedimiento Enlazar un comando a un control sin la compatibilidad de comandos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
ms.openlocfilehash: 5f963c871ed9b600586c32403a288eadd6e9daec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725381"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Procedimiento Enlazar un comando a un control sin la compatibilidad de comandos
En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Input.RoutedCommand> a un <xref:System.Windows.Controls.Control> que no tiene compatibilidad integrada para el comando.  Para obtener un ejemplo completo que enlace comandos a varios orígenes, consulte el ejemplo [Crear un objeto RoutedCommand personalizado](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand).  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una biblioteca de comandos comunes que los programadores de aplicaciones se encuentran con regularidad.  Las clases que constituyen la biblioteca de comandos son: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> y <xref:System.Windows.Documents.EditingCommands>.  
  
 Los objetos <xref:System.Windows.Input.RoutedCommand> estáticos que componen estas clases no proporcionan la lógica del comando.  La lógica del comando está asociada al comando con un objeto <xref:System.Windows.Input.CommandBinding>.  Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen compatibilidad integrada para algunos de los comandos de la biblioteca de comandos.  <xref:System.Windows.Controls.TextBox>, por ejemplo, admite muchos de los comandos de edición de la aplicación, como <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> y <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  El desarrollador de aplicaciones no tiene que hacer nada especial para que estos comandos funcionen con estos controles.  Si <xref:System.Windows.Controls.TextBox> es el destino del comando cuando se ejecuta el comando, controlará el comando mediante el <xref:System.Windows.Input.CommandBinding> que está integrado en el control.  
  
 A continuación se muestra cómo usar un <xref:System.Windows.Controls.Button> como origen para el comando <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  Se crea un <xref:System.Windows.Input.CommandBinding> que asocia los controladores <xref:System.Windows.Input.CanExecuteRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler> especificados con el <xref:System.Windows.Input.RoutedCommand>.  
  
 En primer lugar, se crea el origen del comando.  <xref:System.Windows.Controls.Button> se utiliza como el origen del comando.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Después, se crean <xref:System.Windows.Input.ExecutedRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> simplemente abre <xref:System.Windows.MessageBox> para indicar que se ejecutó el comando.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> establece la propiedad <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> en `true`.  Normalmente, el controlador can execute realizaría comprobaciones más completas para ver si el comando puede ejecutarse en el destino del comando actual.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Por último, se crea <xref:System.Windows.Input.CommandBinding> en la raíz <xref:System.Windows.Window> de la aplicación para asociar los controladores de eventos enrutados al comando <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)
- [Enlazar un comando a un control con la compatibilidad de comandos](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
