---
title: "Cómo: Crear un comando RoutedCommand"
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
helpviewer_keywords: RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 449b55d07aa0119ff23c8642ca83b0989f5b1d4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-routedcommand"></a>Cómo: Crear un comando RoutedCommand
Este ejemplo muestra cómo crear una personalizada <xref:System.Windows.Input.RoutedCommand> y cómo implementar el comando personalizado mediante la creación de un <xref:System.Windows.Input.ExecutedRoutedEventHandler> y un <xref:System.Windows.Input.CanExecuteRoutedEventHandler> y adjuntarlos a un <xref:System.Windows.Input.CommandBinding>.  Para obtener más información sobre los comandos, consulte el [Introducción estableciendo](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## <a name="example"></a>Ejemplo  
 El primer paso para crear un <xref:System.Windows.Input.RoutedCommand> es definir el comando y una instancia del tipo.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 Para poder usar el comando en una aplicación, se deben crear controladores de eventos que definen lo que hace el comando  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 Después, un <xref:System.Windows.Input.CommandBinding> se crea que asocia el comando a los controladores de eventos. El <xref:System.Windows.Input.CommandBinding> se crea en un objeto específico.  Este objeto define el ámbito de la <xref:System.Windows.Input.CommandBinding> en el árbol de elementos  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 El paso final es invocar el comando.  Una manera de invocar un comando es asociarlo con un <xref:System.Windows.Input.ICommandSource>, como un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 Cuando se hace clic en el botón, el <xref:System.Windows.Input.RoutedCommand.Execute%2A> método personalizado <xref:System.Windows.Input.RoutedCommand> se llama.  El <xref:System.Windows.Input.RoutedCommand> provoca la <xref:System.Windows.Input.CommandManager.PreviewExecuted> y <xref:System.Windows.Input.CommandManager.Executed> eventos enrutados.  Estos eventos recorren el árbol de elementos que se busca un <xref:System.Windows.Input.CommandBinding> para ese comando concreto.  Si un <xref:System.Windows.Input.CommandBinding> se encuentra, el <xref:System.Windows.Input.ExecutedRoutedEventHandler> asociada <xref:System.Windows.Input.CommandBinding> se llama.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Input.RoutedCommand>  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)
