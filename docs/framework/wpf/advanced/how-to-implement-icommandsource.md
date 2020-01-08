---
title: 'Cómo: Implementar ICommandSource'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 755377d25a2deb48aa9da86d4182075e30763530
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345099"
---
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="1c782-102">Cómo: Implementar ICommandSource</span><span class="sxs-lookup"><span data-stu-id="1c782-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="1c782-103">En este ejemplo se muestra cómo crear un origen de comando implementando <xref:System.Windows.Input.ICommandSource>.</span><span class="sxs-lookup"><span data-stu-id="1c782-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="1c782-104">Un origen de comando es un objeto que sabe cómo invocar un comando.</span><span class="sxs-lookup"><span data-stu-id="1c782-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="1c782-105">La interfaz <xref:System.Windows.Input.ICommandSource> expone tres miembros:</span><span class="sxs-lookup"><span data-stu-id="1c782-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="1c782-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: el comando que se invocará.</span><span class="sxs-lookup"><span data-stu-id="1c782-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="1c782-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: tipo de datos definido por el usuario que se pasa desde el origen del comando al método que controla el comando.</span><span class="sxs-lookup"><span data-stu-id="1c782-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="1c782-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: el objeto en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="1c782-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="1c782-109">En este ejemplo, se crea una clase que hereda del control <xref:System.Windows.Controls.Slider> e implementa la interfaz <xref:System.Windows.Input.ICommandSource>.</span><span class="sxs-lookup"><span data-stu-id="1c782-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="1c782-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c782-110">Example</span></span>

<span data-ttu-id="1c782-111">WPF proporciona una serie de clases que implementan <xref:System.Windows.Input.ICommandSource>, como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>y <xref:System.Windows.Documents.Hyperlink>.</span><span class="sxs-lookup"><span data-stu-id="1c782-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="1c782-112">Un origen de comando define cómo invoca un comando.</span><span class="sxs-lookup"><span data-stu-id="1c782-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="1c782-113">Estas clases invocan un comando cuando se hace clic en él y solo se convierten en un origen de comando cuando se establece su propiedad <xref:System.Windows.Input.ICommandSource.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c782-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="1c782-114">En este ejemplo, invocará el comando cuando se mueva el control deslizante, o con más precisión, cuando cambie la propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c782-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="1c782-115">A continuación se encuentra la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="1c782-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="1c782-116">El siguiente paso es implementar el <xref:System.Windows.Input.ICommandSource> miembros.</span><span class="sxs-lookup"><span data-stu-id="1c782-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="1c782-117">En este ejemplo, las propiedades se implementan como objetos <xref:System.Windows.DependencyProperty>.</span><span class="sxs-lookup"><span data-stu-id="1c782-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="1c782-118">Esto permite que las propiedades utilicen el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="1c782-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="1c782-119">Para obtener más información sobre la clase <xref:System.Windows.DependencyProperty>, consulte la [información general sobre las propiedades de dependencia](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1c782-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="1c782-120">Para obtener más información sobre el enlace de datos, vea [información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="1c782-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="1c782-121">Aquí solo se muestra la propiedad <xref:System.Windows.Input.ICommandSource.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c782-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="1c782-122">A continuación se indican las devoluciones de llamada de <xref:System.Windows.DependencyProperty> cambio:</span><span class="sxs-lookup"><span data-stu-id="1c782-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="1c782-123">El siguiente paso consiste en agregar y quitar el comando que está asociado con el origen del comando.</span><span class="sxs-lookup"><span data-stu-id="1c782-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="1c782-124">La propiedad <xref:System.Windows.Input.ICommandSource.Command%2A> no se puede sobrescribir simplemente cuando se agrega un nuevo comando, ya que los controladores de eventos asociados al comando anterior, si lo hubiera, se deben quitar primero.</span><span class="sxs-lookup"><span data-stu-id="1c782-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="1c782-125">El siguiente paso consiste en crear una lógica para el controlador de <xref:System.Windows.Input.ICommand.CanExecuteChanged>.</span><span class="sxs-lookup"><span data-stu-id="1c782-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="1c782-126">El evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> notifica al origen del comando que la capacidad del comando para ejecutarse en el destino del comando actual puede haber cambiado.</span><span class="sxs-lookup"><span data-stu-id="1c782-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="1c782-127">Cuando un origen de comando recibe este evento, normalmente llama al método <xref:System.Windows.Input.ICommand.CanExecute%2A> en el comando.</span><span class="sxs-lookup"><span data-stu-id="1c782-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="1c782-128">Si el comando no se puede ejecutar en el destino del comando actual, el origen del comando se deshabilitará normalmente.</span><span class="sxs-lookup"><span data-stu-id="1c782-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="1c782-129">Si el comando se puede ejecutar en el destino del comando actual, el origen del comando se habilitará por lo general.</span><span class="sxs-lookup"><span data-stu-id="1c782-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="1c782-130">El último paso es el método <xref:System.Windows.Input.ICommand.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c782-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="1c782-131">Si el comando es un <xref:System.Windows.Input.RoutedCommand>, se llama al método <xref:System.Windows.Input.RoutedCommand.Execute%2A> <xref:System.Windows.Input.RoutedCommand>; de lo contrario, se llama al método de <xref:System.Windows.Input.ICommand.Execute%2A> de <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="1c782-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="1c782-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c782-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="1c782-133">Información general sobre comandos</span><span class="sxs-lookup"><span data-stu-id="1c782-133">Commanding Overview</span></span>](commanding-overview.md)
