---
title: 'Cómo: Agregar un controlador de eventos mediante código'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e7627589ff7e422c4ad3cd7a37fdc14c8a9c9f4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="76d23-102">Cómo: Agregar un controlador de eventos mediante código</span><span class="sxs-lookup"><span data-stu-id="76d23-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="76d23-103">Este ejemplo muestra cómo agregar un controlador de eventos a un elemento mediante código.</span><span class="sxs-lookup"><span data-stu-id="76d23-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="76d23-104">Si desea agregar un controlador de eventos para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento y a la página de marcado que contiene el elemento ya se ha cargado, debe agregar el controlador mediante código.</span><span class="sxs-lookup"><span data-stu-id="76d23-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="76d23-105">O bien, si está creando el árbol de elementos de una aplicación totalmente mediante código y no se declara ningún elemento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede llamar a métodos específicos para agregar controladores de eventos en el árbol de elementos construido.</span><span class="sxs-lookup"><span data-stu-id="76d23-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76d23-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76d23-106">Example</span></span>  
 <span data-ttu-id="76d23-107">En el ejemplo siguiente se agrega un nuevo <xref:System.Windows.Controls.Button> a una página existente que se define inicialmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d23-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="76d23-108">Un archivo de código subyacente implementa un método de controlador de eventos y, a continuación, agrega ese método como un nuevo controlador de eventos en el <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="76d23-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="76d23-109">El ejemplo de C# se usa el `+=` operador que se va a asignar un controlador a un evento.</span><span class="sxs-lookup"><span data-stu-id="76d23-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="76d23-110">Éste es el mismo operador que se utiliza para asignar un controlador en el [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] modelo de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="76d23-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> <span data-ttu-id="76d23-111">Microsoft Visual Basic no admite este operador como un medio para agregar controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="76d23-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="76d23-112">En su lugar, requiere una de estas dos técnicas:</span><span class="sxs-lookup"><span data-stu-id="76d23-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="76d23-113">Use la <xref:System.Windows.UIElement.AddHandler%2A> método, junto con un `AddressOf` operador, para hacer referencia a la implementación del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="76d23-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="76d23-114">Use la `Handles` palabra clave como parte de la definición de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="76d23-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="76d23-115">Esta técnica no se muestra aquí; vea [Visual Basic y el control de eventos de WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="76d23-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="76d23-116">Agregar un controlador de eventos en el objeto analizado inicialmente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página es mucho más fácil.</span><span class="sxs-lookup"><span data-stu-id="76d23-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="76d23-117">En el elemento de objeto en el que desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="76d23-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="76d23-118">A continuación, especifique el valor de ese atributo como el nombre del método de controlador de eventos que ha definido en el archivo de código subyacente de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página.</span><span class="sxs-lookup"><span data-stu-id="76d23-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="76d23-119">Para obtener más información, consulte [información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) o [enrutan Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="76d23-119">For more information, see [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) or [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d23-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="76d23-120">See Also</span></span>  
 [<span data-ttu-id="76d23-121">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="76d23-121">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="76d23-122">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="76d23-122">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
