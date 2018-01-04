---
title: "Cómo: Enlazar un comando a un control sin la compatibilidad de comandos"
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
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 804c4ffd54a0f8cc94e8849a223b1af8b27a58b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Cómo: Enlazar un comando a un control sin la compatibilidad de comandos
En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Input.RoutedCommand> a un <xref:System.Windows.Controls.Control> que no tienen compatibilidad integrada para el comando.  Para obtener un ejemplo completo que enlace comandos a varios orígenes, consulte el ejemplo [Crear un objeto RoutedCommand personalizado](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una biblioteca de comandos comunes que los programadores de aplicaciones se encuentran con regularidad.  Las clases que constituyen la biblioteca de comandos son: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, y <xref:System.Windows.Documents.EditingCommands>.  
  
 El método estático <xref:System.Windows.Input.RoutedCommand> objetos que componen estas clases no proporcionan la lógica de comandos.  La lógica para el comando está asociada con el comando con un <xref:System.Windows.Input.CommandBinding>.  Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ha creado en la compatibilidad de algunos de los comandos en la biblioteca de comandos.  <xref:System.Windows.Controls.TextBox>, por ejemplo, admite muchos de los comandos de edición de la aplicación, como <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, y <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  El desarrollador de aplicaciones no tiene que hacer nada especial para que estos comandos funcionen con estos controles.  Si el <xref:System.Windows.Controls.TextBox> es el destino del comando cuando se ejecuta el comando, controlará el comando mediante el <xref:System.Windows.Input.CommandBinding> que está integrado en el control.  
  
 La siguiente muestra cómo utilizar un <xref:System.Windows.Controls.Button> como el origen del comando para el <xref:System.Windows.Input.ApplicationCommands.Open%2A> comando.  A <xref:System.Windows.Input.CommandBinding> se crea esa asociación especificado <xref:System.Windows.Input.CanExecuteRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler> con el <xref:System.Windows.Input.RoutedCommand>.  
  
 En primer lugar, se crea el origen del comando.  Un <xref:System.Windows.Controls.Button> se utiliza como el origen del comando.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Después, el <xref:System.Windows.Input.ExecutedRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler> se crean.  El <xref:System.Windows.Input.ExecutedRoutedEventHandler> simplemente abre un <xref:System.Windows.MessageBox> para indicar que se ejecutó el comando.  El <xref:System.Windows.Input.CanExecuteRoutedEventHandler> establece la <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> propiedad `true`.  Normalmente, puede ejecutar controlador realizaría comprobaciones más robustas para ver si el comando puede ejecutarse en el destino del comando actual.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Por último, un <xref:System.Windows.Input.CommandBinding> se crea en la raíz <xref:System.Windows.Window> de la aplicación que asocia los controladores de eventos enrutados para el <xref:System.Windows.Input.ApplicationCommands.Open%2A> comando.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Enlazar un comando a un control con la compatibilidad de comandos](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
