---
title: 'Cómo: Implementar ICommandSource'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174698"
---
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="91010-102">Cómo: Implementar ICommandSource</span><span class="sxs-lookup"><span data-stu-id="91010-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="91010-103">En este ejemplo se muestra cómo <xref:System.Windows.Input.ICommandSource>crear un origen de comandos implementando .</span><span class="sxs-lookup"><span data-stu-id="91010-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="91010-104">Un origen de comandos es un objeto que sabe cómo invocar un comando.</span><span class="sxs-lookup"><span data-stu-id="91010-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="91010-105">La <xref:System.Windows.Input.ICommandSource> interfaz expone tres miembros:</span><span class="sxs-lookup"><span data-stu-id="91010-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="91010-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: el comando que se invocará.</span><span class="sxs-lookup"><span data-stu-id="91010-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="91010-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: un tipo de datos definido por el usuario que se pasa desde el origen del comando al método que controla el comando.</span><span class="sxs-lookup"><span data-stu-id="91010-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="91010-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: el objeto en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="91010-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="91010-109">En este ejemplo, se crea una <xref:System.Windows.Controls.Slider> clase que hereda del control e implementa la <xref:System.Windows.Input.ICommandSource> interfaz.</span><span class="sxs-lookup"><span data-stu-id="91010-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="91010-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91010-110">Example</span></span>

<span data-ttu-id="91010-111">WPFWPF proporciona varias clases <xref:System.Windows.Input.ICommandSource>que <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.MenuItem>implementan <xref:System.Windows.Documents.Hyperlink>, como , , y .</span><span class="sxs-lookup"><span data-stu-id="91010-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="91010-112">Un origen de comandos define cómo invoca un comando.</span><span class="sxs-lookup"><span data-stu-id="91010-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="91010-113">Estas clases invocan un comando cuando se hace clic <xref:System.Windows.Input.ICommandSource.Command%2A> en ellas y solo se convierten en un origen de comandos cuando se establece su propiedad.</span><span class="sxs-lookup"><span data-stu-id="91010-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="91010-114">En este ejemplo, invocará el comando cuando se mueva el <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> control deslizante, o más exactamente, cuando se cambie la propiedad.</span><span class="sxs-lookup"><span data-stu-id="91010-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="91010-115">La siguiente es la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="91010-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="91010-116">El siguiente paso es <xref:System.Windows.Input.ICommandSource> implementar los miembros.</span><span class="sxs-lookup"><span data-stu-id="91010-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="91010-117">En este ejemplo, las propiedades <xref:System.Windows.DependencyProperty> se implementan como objetos.</span><span class="sxs-lookup"><span data-stu-id="91010-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="91010-118">Esto permite que las propiedades usen el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="91010-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="91010-119">Para obtener más <xref:System.Windows.DependencyProperty> información acerca de la clase, vea [Información general](dependency-properties-overview.md)sobre propiedades de dependencia .</span><span class="sxs-lookup"><span data-stu-id="91010-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="91010-120">Para obtener más información sobre el enlace de datos, vea [Información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos .</span><span class="sxs-lookup"><span data-stu-id="91010-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="91010-121">Aquí <xref:System.Windows.Input.ICommandSource.Command%2A> solo se muestra la propiedad.</span><span class="sxs-lookup"><span data-stu-id="91010-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="91010-122">A continuación <xref:System.Windows.DependencyProperty> se muestra la devolución de llamada de cambio:</span><span class="sxs-lookup"><span data-stu-id="91010-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="91010-123">El siguiente paso es agregar y quitar el comando que está asociado con el origen del comando.</span><span class="sxs-lookup"><span data-stu-id="91010-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="91010-124">La <xref:System.Windows.Input.ICommandSource.Command%2A> propiedad no se puede sobrescribir simplemente cuando se agrega un nuevo comando, porque los controladores de eventos asociados con el comando anterior, si lo hubo, deben quitarse primero.</span><span class="sxs-lookup"><span data-stu-id="91010-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="91010-125">El siguiente paso es crear <xref:System.Windows.Input.ICommand.CanExecuteChanged> lógica para el controlador.</span><span class="sxs-lookup"><span data-stu-id="91010-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="91010-126">El <xref:System.Windows.Input.ICommand.CanExecuteChanged> evento notifica al origen del comando que la capacidad del comando para ejecutarse en el destino del comando actual puede haber cambiado.</span><span class="sxs-lookup"><span data-stu-id="91010-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="91010-127">Cuando un origen de comandos recibe este <xref:System.Windows.Input.ICommand.CanExecute%2A> evento, normalmente llama al método en el comando.</span><span class="sxs-lookup"><span data-stu-id="91010-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="91010-128">Si el comando no se puede ejecutar en el destino del comando actual, el origen del comando normalmente se deshabilitará a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="91010-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="91010-129">Si el comando se puede ejecutar en el destino del comando actual, el origen del comando normalmente se habilitará a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="91010-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="91010-130">El último paso <xref:System.Windows.Input.ICommand.Execute%2A> es el método.</span><span class="sxs-lookup"><span data-stu-id="91010-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="91010-131">Si el comando <xref:System.Windows.Input.RoutedCommand>es <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> un , se llama al método; de lo <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> contrario, se llama al método.</span><span class="sxs-lookup"><span data-stu-id="91010-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="91010-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91010-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="91010-133">Información general sobre comandos</span><span class="sxs-lookup"><span data-stu-id="91010-133">Commanding Overview</span></span>](commanding-overview.md)
