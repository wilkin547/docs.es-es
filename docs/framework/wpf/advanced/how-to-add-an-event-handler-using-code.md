---
title: Procedimiento Agregar un controlador de eventos mediante código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 017b32dc07f62cc4553a84f7b91687fb34a53c65
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937469"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="f8d2b-102">Procedimiento Agregar un controlador de eventos mediante código</span><span class="sxs-lookup"><span data-stu-id="f8d2b-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="f8d2b-103">En este ejemplo se muestra cómo agregar un controlador de eventos a un elemento mediante código.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="f8d2b-104">Si desea agregar un controlador de eventos a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento y la página de marcado que contiene el elemento ya se ha cargado, debe agregar el controlador mediante código.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="f8d2b-105">Como alternativa, si va a crear el árbol de elementos para una aplicación que utiliza el código completamente y no declara ningún elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]mediante, puede llamar a métodos específicos para agregar controladores de eventos al árbol de elementos construido.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8d2b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8d2b-106">Example</span></span>  
 <span data-ttu-id="f8d2b-107">En el ejemplo siguiente se agrega <xref:System.Windows.Controls.Button> un nuevo a una página existente que se define [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]inicialmente en.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="f8d2b-108">Un archivo de código subyacente implementa un método de controlador de eventos y, a continuación, agrega ese método como un nuevo <xref:System.Windows.Controls.Button>controlador de eventos en.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="f8d2b-109">En C# el ejemplo se `+=` usa el operador para asignar un controlador a un evento.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="f8d2b-110">Es el mismo operador que se utiliza para asignar un controlador en el modelo de control de eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f8d2b-110">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="f8d2b-111">Microsoft Visual Basic no admite este operador como medio para agregar controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="f8d2b-112">En su lugar, requiere una de estas dos técnicas:</span><span class="sxs-lookup"><span data-stu-id="f8d2b-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="f8d2b-113">Use el <xref:System.Windows.UIElement.AddHandler%2A> método, junto con un `AddressOf` operador, para hacer referencia a la implementación del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="f8d2b-114">Use la `Handles` palabra clave como parte de la definición del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="f8d2b-115">Esta técnica no se muestra aquí. vea [control de eventos de Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="f8d2b-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="f8d2b-116">Agregar un controlador de eventos en la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página analizada inicialmente es mucho más sencillo.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="f8d2b-117">En el elemento de objeto en el que desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="f8d2b-118">A continuación, especifique el valor de ese atributo como el nombre del método de control de eventos que definió en el archivo de código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] subyacente de la página.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="f8d2b-119">Para obtener más información, vea información general sobre [XAML (WPF)](xaml-overview-wpf.md) o [información general sobre eventos](routed-events-overview.md)enrutados.</span><span class="sxs-lookup"><span data-stu-id="f8d2b-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d2b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8d2b-120">See also</span></span>

- [<span data-ttu-id="f8d2b-121">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="f8d2b-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="f8d2b-122">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="f8d2b-122">How-to Topics</span></span>](events-how-to-topics.md)
