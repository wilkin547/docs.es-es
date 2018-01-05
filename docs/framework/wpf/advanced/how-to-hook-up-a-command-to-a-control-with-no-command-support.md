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
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a><span data-ttu-id="a5717-102">Cómo: Enlazar un comando a un control sin la compatibilidad de comandos</span><span class="sxs-lookup"><span data-stu-id="a5717-102">How to: Hook Up a Command to a Control with No Command Support</span></span>
<span data-ttu-id="a5717-103">En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Input.RoutedCommand> a un <xref:System.Windows.Controls.Control> que no tienen compatibilidad integrada para el comando.</span><span class="sxs-lookup"><span data-stu-id="a5717-103">The following example shows how to hook up a <xref:System.Windows.Input.RoutedCommand> to a <xref:System.Windows.Controls.Control> which does not have built in support for the command.</span></span>  <span data-ttu-id="a5717-104">Para obtener un ejemplo completo que enlace comandos a varios orígenes, consulte el ejemplo [Crear un objeto RoutedCommand personalizado](http://go.microsoft.com/fwlink/?LinkID=159980).</span><span class="sxs-lookup"><span data-stu-id="a5717-104">For a complete sample which hooks up commands to multiple sources, see the [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980) sample.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5717-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5717-105">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="a5717-106"> proporciona una biblioteca de comandos comunes que los programadores de aplicaciones se encuentran con regularidad.</span><span class="sxs-lookup"><span data-stu-id="a5717-106"> provides a library of common commands which application programmers encounter regularly.</span></span>  <span data-ttu-id="a5717-107">Las clases que constituyen la biblioteca de comandos son: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, y <xref:System.Windows.Documents.EditingCommands>.</span><span class="sxs-lookup"><span data-stu-id="a5717-107">The classes which comprise the command library are: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, and <xref:System.Windows.Documents.EditingCommands>.</span></span>  
  
 <span data-ttu-id="a5717-108">El método estático <xref:System.Windows.Input.RoutedCommand> objetos que componen estas clases no proporcionan la lógica de comandos.</span><span class="sxs-lookup"><span data-stu-id="a5717-108">The static <xref:System.Windows.Input.RoutedCommand> objects which make up these classes do not supply command logic.</span></span>  <span data-ttu-id="a5717-109">La lógica para el comando está asociada con el comando con un <xref:System.Windows.Input.CommandBinding>.</span><span class="sxs-lookup"><span data-stu-id="a5717-109">The logic for the command is associated with the command with a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="a5717-110">Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ha creado en la compatibilidad de algunos de los comandos en la biblioteca de comandos.</span><span class="sxs-lookup"><span data-stu-id="a5717-110">Many controls in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] have built in support for some of the commands in the command library.</span></span>  <span data-ttu-id="a5717-111"><xref:System.Windows.Controls.TextBox>, por ejemplo, admite muchos de los comandos de edición de la aplicación, como <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, y <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5717-111"><xref:System.Windows.Controls.TextBox>, for example, supports many of the application edit commands such as <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, and <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.</span></span>  <span data-ttu-id="a5717-112">El desarrollador de aplicaciones no tiene que hacer nada especial para que estos comandos funcionen con estos controles.</span><span class="sxs-lookup"><span data-stu-id="a5717-112">The application developer does not have to do anything special to get these commands to work with these controls.</span></span>  <span data-ttu-id="a5717-113">Si el <xref:System.Windows.Controls.TextBox> es el destino del comando cuando se ejecuta el comando, controlará el comando mediante el <xref:System.Windows.Input.CommandBinding> que está integrado en el control.</span><span class="sxs-lookup"><span data-stu-id="a5717-113">If the <xref:System.Windows.Controls.TextBox> is the command target when the command is executed, it will handle the command using the <xref:System.Windows.Input.CommandBinding> that is built into the control.</span></span>  
  
 <span data-ttu-id="a5717-114">La siguiente muestra cómo utilizar un <xref:System.Windows.Controls.Button> como el origen del comando para el <xref:System.Windows.Input.ApplicationCommands.Open%2A> comando.</span><span class="sxs-lookup"><span data-stu-id="a5717-114">The following shows how to use a <xref:System.Windows.Controls.Button> as the command source for the <xref:System.Windows.Input.ApplicationCommands.Open%2A> command.</span></span>  <span data-ttu-id="a5717-115">A <xref:System.Windows.Input.CommandBinding> se crea esa asociación especificado <xref:System.Windows.Input.CanExecuteRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler> con el <xref:System.Windows.Input.RoutedCommand>.</span><span class="sxs-lookup"><span data-stu-id="a5717-115">A <xref:System.Windows.Input.CommandBinding> is created that associates the specified <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and the <xref:System.Windows.Input.CanExecuteRoutedEventHandler> with the <xref:System.Windows.Input.RoutedCommand>.</span></span>  
  
 <span data-ttu-id="a5717-116">En primer lugar, se crea el origen del comando.</span><span class="sxs-lookup"><span data-stu-id="a5717-116">First, the command source is created.</span></span>  <span data-ttu-id="a5717-117">Un <xref:System.Windows.Controls.Button> se utiliza como el origen del comando.</span><span class="sxs-lookup"><span data-stu-id="a5717-117">A <xref:System.Windows.Controls.Button> is used as the command source.</span></span>  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 <span data-ttu-id="a5717-118">Después, el <xref:System.Windows.Input.ExecutedRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler> se crean.</span><span class="sxs-lookup"><span data-stu-id="a5717-118">Next, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> and the <xref:System.Windows.Input.CanExecuteRoutedEventHandler> are created.</span></span>  <span data-ttu-id="a5717-119">El <xref:System.Windows.Input.ExecutedRoutedEventHandler> simplemente abre un <xref:System.Windows.MessageBox> para indicar que se ejecutó el comando.</span><span class="sxs-lookup"><span data-stu-id="a5717-119">The <xref:System.Windows.Input.ExecutedRoutedEventHandler> simply opens a <xref:System.Windows.MessageBox> to signify that the command executed.</span></span>  <span data-ttu-id="a5717-120">El <xref:System.Windows.Input.CanExecuteRoutedEventHandler> establece la <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="a5717-120">The <xref:System.Windows.Input.CanExecuteRoutedEventHandler> sets the <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> property to `true`.</span></span>  <span data-ttu-id="a5717-121">Normalmente, puede ejecutar controlador realizaría comprobaciones más robustas para ver si el comando puede ejecutarse en el destino del comando actual.</span><span class="sxs-lookup"><span data-stu-id="a5717-121">Normally, the can execute handler would perform more robust checks to see if the command could execute on the current command target.</span></span>  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 <span data-ttu-id="a5717-122">Por último, un <xref:System.Windows.Input.CommandBinding> se crea en la raíz <xref:System.Windows.Window> de la aplicación que asocia los controladores de eventos enrutados para el <xref:System.Windows.Input.ApplicationCommands.Open%2A> comando.</span><span class="sxs-lookup"><span data-stu-id="a5717-122">Finally, a <xref:System.Windows.Input.CommandBinding> is created on the root <xref:System.Windows.Window> of the application that associates the routed events handlers to the <xref:System.Windows.Input.ApplicationCommands.Open%2A> command.</span></span>  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a><span data-ttu-id="a5717-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5717-123">See Also</span></span>  
 [<span data-ttu-id="a5717-124">Información general sobre comandos</span><span class="sxs-lookup"><span data-stu-id="a5717-124">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [<span data-ttu-id="a5717-125">Enlazar un comando a un control con la compatibilidad de comandos</span><span class="sxs-lookup"><span data-stu-id="a5717-125">Hook Up a Command to a Control with Command Support</span></span>](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
