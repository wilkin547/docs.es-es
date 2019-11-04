---
title: 'Cómo: Agregar un controlador de eventos mediante código'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460433"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="7cc5f-102">Cómo: Agregar un controlador de eventos mediante código</span><span class="sxs-lookup"><span data-stu-id="7cc5f-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="7cc5f-103">En este ejemplo se muestra cómo agregar un controlador de eventos a un elemento mediante código.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="7cc5f-104">Si desea agregar un controlador de eventos a un elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y la página de marcado que contiene el elemento ya se ha cargado, debe agregar el controlador mediante código.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="7cc5f-105">Como alternativa, si va a crear el árbol de elementos para una aplicación que usa el código completamente y no declara ningún elemento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede llamar a métodos específicos para agregar controladores de eventos al árbol de elementos construido.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cc5f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cc5f-106">Example</span></span>  
 <span data-ttu-id="7cc5f-107">En el ejemplo siguiente se agrega un nuevo <xref:System.Windows.Controls.Button> a una página existente que se define inicialmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cc5f-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="7cc5f-108">Un archivo de código subyacente implementa un método de controlador de eventos y, a continuación, agrega ese método como un nuevo controlador de eventos en el <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="7cc5f-109">En C# el ejemplo se usa el operador `+=` para asignar un controlador a un evento.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="7cc5f-110">Es el mismo operador que se utiliza para asignar un controlador en el modelo de control de eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7cc5f-110">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="7cc5f-111">Microsoft Visual Basic no admite este operador como medio para agregar controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="7cc5f-112">En su lugar, requiere una de estas dos técnicas:</span><span class="sxs-lookup"><span data-stu-id="7cc5f-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="7cc5f-113">Utilice el método <xref:System.Windows.UIElement.AddHandler%2A>, junto con un operador `AddressOf`, para hacer referencia a la implementación del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="7cc5f-114">Use la palabra clave `Handles` como parte de la definición del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="7cc5f-115">Esta técnica no se muestra aquí. vea [control de eventos de Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="7cc5f-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="7cc5f-116">Agregar un controlador de eventos en la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] analizada inicialmente es mucho más sencillo.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="7cc5f-117">En el elemento de objeto en el que desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="7cc5f-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="7cc5f-118">A continuación, especifique el valor de ese atributo como el nombre del método de control de eventos que definió en el archivo de código subyacente de la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cc5f-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="7cc5f-119">Para obtener más información, vea información general sobre [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) o [información general sobre eventos enrutados](routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7cc5f-119">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc5f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cc5f-120">See also</span></span>

- [<span data-ttu-id="7cc5f-121">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="7cc5f-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="7cc5f-122">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="7cc5f-122">How-to Topics</span></span>](events-how-to-topics.md)
