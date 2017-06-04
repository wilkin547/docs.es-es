---
title: "C&#243;mo: Crear un comando RoutedCommand | Microsoft Docs"
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
  - "clases, RoutedCommand, crear"
  - "crear, RoutedCommand (clase)"
  - "RoutedCommand (clase), crear"
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Crear un comando RoutedCommand
En este ejemplo se muestra cómo crear un comando <xref:System.Windows.Input.RoutedCommand> personalizado y cómo implementarlo creando un controlador <xref:System.Windows.Input.ExecutedRoutedEventHandler> y un controlador <xref:System.Windows.Input.CanExecuteRoutedEventHandler> y asociándolos a un enlace <xref:System.Windows.Input.CommandBinding>.  Para obtener más información sobre los comandos, vea [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## Ejemplo  
 El primer paso para crear <xref:System.Windows.Input.RoutedCommand> es definir el comando y crear una instancia de él.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 Para utilizar el comando en una aplicación, es preciso crear los controladores de eventos que definen qué hace el comando  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 Luego, se crea un enlace <xref:System.Windows.Input.CommandBinding> que asocia el comando a los controladores de eventos.  <xref:System.Windows.Input.CommandBinding> se crea para un objeto concreto.  Este objeto define el ámbito de <xref:System.Windows.Input.CommandBinding> en el árbol de elementos  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 El paso final consiste en invocar el comando.  Una manera de invocar un comando es asociarlo a una interfaz <xref:System.Windows.Input.ICommandSource>, como un <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 Cuando se hace clic en el objeto Button, se llama al método <xref:System.Windows.Input.RoutedCommand.Execute%2A> del comando <xref:System.Windows.Input.RoutedCommand> personalizado.  <xref:System.Windows.Input.RoutedCommand> provoca los eventos enrutados <xref:System.Windows.Input.CommandManager.PreviewExecuted> y <xref:System.Windows.Input.CommandManager.Executed>.  Estos eventos recorren el árbol de elementos en busca de un enlace <xref:System.Windows.Input.CommandBinding> para ese comando concreto.  Si se encuentra un enlace <xref:System.Windows.Input.CommandBinding>, se llama al controlador <xref:System.Windows.Input.ExecutedRoutedEventHandler> asociado a <xref:System.Windows.Input.CommandBinding>.  
  
## Vea también  
 <xref:System.Windows.Input.RoutedCommand>   
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)