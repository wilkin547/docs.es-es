---
title: Procedimiento Crear un comando RoutedCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: 73a5337cae61a38e10f3ddd7dbe654d7fae616b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735745"
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="7a572-102">Procedimiento Crear un comando RoutedCommand</span><span class="sxs-lookup"><span data-stu-id="7a572-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="7a572-103">En este ejemplo se muestra cómo crear una personalizada <xref:System.Windows.Input.RoutedCommand> y cómo implementar el comando personalizado mediante la creación de un <xref:System.Windows.Input.ExecutedRoutedEventHandler> y un <xref:System.Windows.Input.CanExecuteRoutedEventHandler> y adjuntarlos a un <xref:System.Windows.Input.CommandBinding>.</span><span class="sxs-lookup"><span data-stu-id="7a572-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="7a572-104">Para obtener más información sobre los comandos, consulte el [información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7a572-104">For more information on commanding, see the [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a572-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a572-105">Example</span></span>  
 <span data-ttu-id="7a572-106">El primer paso para crear un <xref:System.Windows.Input.RoutedCommand> es definir el comando y sus instancias.</span><span class="sxs-lookup"><span data-stu-id="7a572-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="7a572-107">Para poder usar el comando en una aplicación, se deben crear controladores de eventos que definen lo que hace el comando</span><span class="sxs-lookup"><span data-stu-id="7a572-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="7a572-108">A continuación, un <xref:System.Windows.Input.CommandBinding> se crea que asocia el comando con los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="7a572-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="7a572-109">El <xref:System.Windows.Input.CommandBinding> se crea en un objeto específico.</span><span class="sxs-lookup"><span data-stu-id="7a572-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="7a572-110">Este objeto define el ámbito de la <xref:System.Windows.Input.CommandBinding> en el árbol de elementos</span><span class="sxs-lookup"><span data-stu-id="7a572-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="7a572-111">El último paso es invocar el comando.</span><span class="sxs-lookup"><span data-stu-id="7a572-111">The final step is invoking the command.</span></span>  <span data-ttu-id="7a572-112">Es una manera de invocar un comando asociarlo con un <xref:System.Windows.Input.ICommandSource>, como un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="7a572-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="7a572-113">Cuando se hace clic en el botón, el <xref:System.Windows.Input.RoutedCommand.Execute%2A> método personalizado <xref:System.Windows.Input.RoutedCommand> se llama.</span><span class="sxs-lookup"><span data-stu-id="7a572-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="7a572-114">El <xref:System.Windows.Input.RoutedCommand> provoca la <xref:System.Windows.Input.CommandManager.PreviewExecuted> y <xref:System.Windows.Input.CommandManager.Executed> eventos enrutados.</span><span class="sxs-lookup"><span data-stu-id="7a572-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="7a572-115">Estos eventos recorren el árbol de elementos que busca un <xref:System.Windows.Input.CommandBinding> para ese comando concreto.</span><span class="sxs-lookup"><span data-stu-id="7a572-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="7a572-116">Si un <xref:System.Windows.Input.CommandBinding> se encuentra, el <xref:System.Windows.Input.ExecutedRoutedEventHandler> asociado <xref:System.Windows.Input.CommandBinding> se llama.</span><span class="sxs-lookup"><span data-stu-id="7a572-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a572-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a572-117">See also</span></span>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="7a572-118">Información general sobre comandos</span><span class="sxs-lookup"><span data-stu-id="7a572-118">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)
