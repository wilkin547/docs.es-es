---
title: "C&#243;mo: Enlazar un comando a un control sin la compatibilidad de comandos | Microsoft Docs"
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
  - "clases, Control, asociar RoutedCommand"
  - "clases, RoutedCommand, asociar a un control"
  - "Control (clase), asociar RoutedCommand"
  - "RoutedCommand (clase), asociar a un control"
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Enlazar un comando a un control sin la compatibilidad de comandos
En el ejemplo siguiente se muestra cómo enlazar <xref:System.Windows.Input.RoutedCommand> a un objeto <xref:System.Windows.Controls.Control> que no tiene compatibilidad integrada para el comando.  Para obtener un ejemplo completo que enlaza comandos a varios orígenes, vea el ejemplo [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una biblioteca de comandos comunes que los programadores de aplicaciones suelen utilizar.  Las clases que componen la biblioteca de comandos son: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> y <xref:System.Windows.Documents.EditingCommands>.  
  
 Los objetos <xref:System.Windows.Input.RoutedCommand> estáticos que componen estas clases no proporcionan la lógica de los comandos.  La lógica del comando se asocia al comando mediante <xref:System.Windows.Input.CommandBinding>.  Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen compatibilidad integrada con algunos de los comandos de la biblioteca de comandos.  Por ejemplo, <xref:System.Windows.Controls.TextBox> admite muchos de los comandos de edición de aplicación, tales como <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> y <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  El programador de aplicaciones no tiene que hacer nada especial para que estos comandos funcionen con estos controles.  Si el control <xref:System.Windows.Controls.TextBox> es el destino del comando al ejecutar éste último, administrará el comando mediante el objeto <xref:System.Windows.Input.CommandBinding> integrado en el control.  
  
 A continuación se muestra cómo utilizar un control <xref:System.Windows.Controls.Button> como origen de comando del comando <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  Se crea un objeto <xref:System.Windows.Input.CommandBinding> que asocia el controlador <xref:System.Windows.Input.CanExecuteRoutedEventHandler> especificado, y <xref:System.Windows.Input.CanExecuteRoutedEventHandler> a <xref:System.Windows.Input.RoutedCommand>.  
  
 Primero, se crea el origen del comando.  <xref:System.Windows.Controls.Button> se utiliza como origen del comando.  
  
 [!code-xml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 A continuación, se crean <xref:System.Windows.Input.ExecutedRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  El controlador <xref:System.Windows.Input.ExecutedRoutedEventHandler> abre un <xref:System.Windows.MessageBox> para indicar que se ejecutó el comando.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> establece la propiedad <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> en `true`.  Normalmente, el controlador de posibilidad de ejecución realizaría comprobaciones más robustas para ver si el comando se pudo ejecutar en el destino de comando actual.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Por último, se crea un objeto <xref:System.Windows.Input.CommandBinding> en el elemento <xref:System.Windows.Window> raíz de la aplicación que asocia los controladores de eventos enrutados al comando <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  
  
 [!code-xml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## Vea también  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Enlazar un comando a un control con la compatibilidad de comandos](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)