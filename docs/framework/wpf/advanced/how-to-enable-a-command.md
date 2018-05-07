---
title: 'Cómo: Habilitar un comando'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
ms.openlocfilehash: 81ae2e46c4fdd8b46e2b72b9a1430437ebfe97b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-a-command"></a>Cómo: Habilitar un comando
En el ejemplo siguiente se muestra cómo utilizar comandos en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  En el ejemplo se muestra cómo asociar un <xref:System.Windows.Input.RoutedCommand> a una <xref:System.Windows.Controls.Button>, cree un <xref:System.Windows.Input.CommandBinding>y crear los controladores de eventos que implementan el <xref:System.Windows.Input.RoutedCommand>.  Para obtener más información sobre los comandos, consulte el [Introducción estableciendo](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## <a name="example"></a>Ejemplo  
 La primera sección de código crea el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], que consta de un <xref:System.Windows.Controls.Button> y un <xref:System.Windows.Controls.StackPanel>y crea un <xref:System.Windows.Input.CommandBinding> que asocia los controladores de comando con el <xref:System.Windows.Input.RoutedCommand>.  
  
 El <xref:System.Windows.Input.ICommandSource.Command%2A> propiedad de la <xref:System.Windows.Controls.Button> está asociado el <xref:System.Windows.Input.ApplicationCommands.Close%2A> comando.  
  
 El <xref:System.Windows.Input.CommandBinding> se agrega a la <xref:System.Windows.Input.CommandBindingCollection> de la raíz <xref:System.Windows.Window>. El <xref:System.Windows.Input.CommandBinding.Executed> y <xref:System.Windows.Input.CommandBinding.CanExecute> controladores de eventos se adjunta a este enlace y se asocian con la <xref:System.Windows.Input.ApplicationCommands.Close%2A> comando.  
  
 Sin el <xref:System.Windows.Input.CommandBinding> hay una lógica de comando, únicamente un mecanismo para invocar el comando.  Cuando el <xref:System.Windows.Controls.Button> se hace clic, el <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> se genera en el destino del comando seguido por el <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.  Estos eventos recorren el árbol de elementos que se busca un <xref:System.Windows.Input.CommandBinding> para ese comando concreto.  Merece la pena mencionar que porque <xref:System.Windows.RoutedEvent> túnel y propagarse a través del árbol de elementos, se debe tener cuidado en donde el <xref:System.Windows.Input.CommandBinding> se coloca.   Si el <xref:System.Windows.Input.CommandBinding> se encuentra en el mismo nivel que el destino del comando o en otro nodo que no está en la ruta de la <xref:System.Windows.RoutedEvent>, el <xref:System.Windows.Input.CommandBinding> no tendrá acceso.  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 La siguiente sección de código implementa la <xref:System.Windows.Input.CommandManager.Executed> y <xref:System.Windows.Input.CommandBinding.CanExecute> controladores de eventos.  
  
 El <xref:System.Windows.Input.CommandManager.Executed> controlador llama a un método para cerrar el archivo abierto.  El <xref:System.Windows.Input.CommandBinding.CanExecute> controlador llama a un método para determinar si un archivo está abierto.  Si un archivo está abierto, <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> está establecido en `true`; en caso contrario, se establece en `false`.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)
