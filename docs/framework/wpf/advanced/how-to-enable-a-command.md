---
title: "C&#243;mo: Habilitar un comando | Microsoft Docs"
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
  - "CommandBindings"
  - "comandos"
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Habilitar un comando
En el siguiente ejemplo se muestra cómo utilizar comandos en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  En el ejemplo se muestra cómo asociar un comando <xref:System.Windows.Input.RoutedCommand> a un control <xref:System.Windows.Controls.Button>, crear un objeto <xref:System.Windows.Input.CommandBinding>y crear los controladores de eventos que implementan <xref:System.Windows.Input.RoutedCommand>.  Para obtener más información sobre los comandos, vea [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## Ejemplo  
 En la primera sección de código se crea la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], que está compuesta de un control <xref:System.Windows.Controls.Button> y un control <xref:System.Windows.Controls.StackPanel>, y se crea también un objeto <xref:System.Windows.Input.CommandBinding> que asocia los controladores de comando a un comando <xref:System.Windows.Input.RoutedCommand>.  
  
 La propiedad <xref:System.Windows.Input.ICommandSource.Command%2A> de <xref:System.Windows.Controls.Button> se asocia al comando <xref:System.Windows.Input.ApplicationCommands.Close%2A>.  
  
 El objeto <xref:System.Windows.Input.CommandBinding> se agrega al objeto <xref:System.Windows.Input.CommandBindingCollection> del objeto <xref:System.Windows.Window> raíz.  Los controladores de eventos <xref:System.Windows.Input.CommandBinding.Executed> y <xref:System.Windows.Input.CommandBinding.CanExecute> se asocian a este enlace y al comando <xref:System.Windows.Input.ApplicationCommands.Close%2A>.  
  
 Sin <xref:System.Windows.Input.CommandBinding> no hay ninguna lógica de comando, únicamente un mecanismo para invocar el comando.  Cuando se hace clic en <xref:System.Windows.Controls.Button>, se provoca el evento <xref:System.Windows.Input.CommandManager.PreviewExecuted> asociado al comando <xref:System.Windows.RoutedEvent> en el destino del comando, seguido por el evento <xref:System.Windows.Input.CommandManager.Executed> asociado al comando <xref:System.Windows.RoutedEvent>.  Estos eventos recorren el árbol de elementos en busca de un enlace <xref:System.Windows.Input.CommandBinding> para ese comando concreto.  Cabe destacar que, debido a que <xref:System.Windows.RoutedEvent> tuneliza y traspasa el árbol de elementos, se deben extremar las precauciones al elegir el lugar donde se coloca <xref:System.Windows.Input.CommandBinding>.  Si <xref:System.Windows.Input.CommandBinding> está en un nodo relacionado con el destino del comando o en otro nodo que no está en la ruta de <xref:System.Windows.RoutedEvent>, no se tendrá acceso a <xref:System.Windows.Input.CommandBinding>.  
  
 [!code-xml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 En la sección de código siguiente se implementan los controladores de eventos <xref:System.Windows.Input.CommandManager.Executed> y <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 El controlador <xref:System.Windows.Input.CommandManager.Executed> llama a un método para cerrar el archivo abierto.  El controlador <xref:System.Windows.Input.CommandBinding.CanExecute> llama a un método para determinar si un archivo está abierto.  Si hay un archivo abierto, la propiedad <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> se establece en `true`; de lo contrario, se establece en `false`.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## Vea también  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)