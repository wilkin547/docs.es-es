---
title: 'Cómo: Agregar un controlador de eventos mediante código'
description: Use este ejemplo para aprender a agregar un controlador de eventos a un elemento en Windows Presentation Foundation mediante el uso de código, en lugar de declararlo mediante XAML.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: b36969f7a65ccbf6c9d03b22767d9eacdc177ad1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166364"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="bd9ce-103">Cómo: Agregar un controlador de eventos mediante código</span><span class="sxs-lookup"><span data-stu-id="bd9ce-103">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="bd9ce-104">En este ejemplo se muestra cómo agregar un controlador de eventos a un elemento mediante código.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-104">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="bd9ce-105">Si desea agregar un controlador de eventos a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento y la página de marcado que contiene el elemento ya se ha cargado, debe agregar el controlador mediante código.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-105">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="bd9ce-106">Como alternativa, si va a crear el árbol de elementos para una aplicación que utiliza el código completamente y no declara ningún elemento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , puede llamar a métodos específicos para agregar controladores de eventos al árbol de elementos construido.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-106">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd9ce-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd9ce-107">Example</span></span>  
 <span data-ttu-id="bd9ce-108">En el ejemplo siguiente se agrega un nuevo <xref:System.Windows.Controls.Button> a una página existente que se define inicialmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd9ce-108">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="bd9ce-109">Un archivo de código subyacente implementa un método de controlador de eventos y, a continuación, agrega ese método como un nuevo controlador de eventos en <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="bd9ce-109">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="bd9ce-110">En el ejemplo de C# `+=` se usa el operador para asignar un controlador a un evento.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-110">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="bd9ce-111">Es el mismo operador que se utiliza para asignar un controlador en el modelo de control de eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bd9ce-111">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="bd9ce-112">Microsoft Visual Basic no admite este operador como medio para agregar controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-112">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="bd9ce-113">En su lugar, requiere una de estas dos técnicas:</span><span class="sxs-lookup"><span data-stu-id="bd9ce-113">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="bd9ce-114">Use el <xref:System.Windows.UIElement.AddHandler%2A> método, junto con un `AddressOf` operador, para hacer referencia a la implementación del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-114">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="bd9ce-115">Use la `Handles` palabra clave como parte de la definición del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-115">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="bd9ce-116">Esta técnica no se muestra aquí. vea [control de eventos de Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="bd9ce-116">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="bd9ce-117">Agregar un controlador de eventos en la página analizada inicialmente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es mucho más sencillo.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-117">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="bd9ce-118">En el elemento de objeto en el que desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-118">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="bd9ce-119">A continuación, especifique el valor de ese atributo como el nombre del método de control de eventos que definió en el archivo de código subyacente de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página.</span><span class="sxs-lookup"><span data-stu-id="bd9ce-119">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="bd9ce-120">Para obtener más información, vea información general sobre [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) o [información general sobre eventos enrutados](routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bd9ce-120">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9ce-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd9ce-121">See also</span></span>

- [<span data-ttu-id="bd9ce-122">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="bd9ce-122">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="bd9ce-123">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="bd9ce-123">How-to Topics</span></span>](events-how-to-topics.md)
