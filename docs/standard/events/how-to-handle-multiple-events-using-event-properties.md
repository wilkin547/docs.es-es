---
title: Procedimiento para controlar varios eventos mediante las propiedades de evento
description: Aprenda a controlar varios eventos mediante propiedades de eventos. Defina colecciones de delegados, claves de eventos y propiedades de evento. Implemente los métodos de descriptor de acceso Add y Remove.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET]
- multiple events [.NET]
- event handling [.NET], with multiple events
- events [.NET], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: 7484ad06e80e6ce131f48431fbdd1e812ce0bfa0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734327"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="04dd1-105">Procedimiento para controlar varios eventos mediante las propiedades de evento</span><span class="sxs-lookup"><span data-stu-id="04dd1-105">How to: Handle Multiple Events Using Event Properties</span></span>

<span data-ttu-id="04dd1-106">Para poder utilizar propiedades de evento, hay que definirlas en la clase que provoca los eventos y, a continuación, establecer los delegados de las propiedades de evento en las clases que controlan los eventos.</span><span class="sxs-lookup"><span data-stu-id="04dd1-106">To use event properties, you define the event properties in the class that raises the events, and then set the delegates for the event properties in classes that handle the events.</span></span> <span data-ttu-id="04dd1-107">Para implementar varias propiedades de evento en una clase, esta clase deberá almacenar internamente y mantener el delegado definido para cada evento.</span><span class="sxs-lookup"><span data-stu-id="04dd1-107">To implement multiple event properties in a class, the class must internally store and maintain the delegate defined for each event.</span></span> <span data-ttu-id="04dd1-108">Para hacerlo, uno de los enfoques típicos consiste en implementar una colección de delegados que se indice por medio de una clave de evento.</span><span class="sxs-lookup"><span data-stu-id="04dd1-108">A typical approach is to implement a delegate collection that is indexed by an event key.</span></span>  
  
 <span data-ttu-id="04dd1-109">Para almacenar los delegados de cada evento, puede utilizar la clase <xref:System.ComponentModel.EventHandlerList> o implementar su propia colección.</span><span class="sxs-lookup"><span data-stu-id="04dd1-109">To store the delegates for each event, you can use the <xref:System.ComponentModel.EventHandlerList> class, or implement your own collection.</span></span> <span data-ttu-id="04dd1-110">La clase de colección debe proporcionar métodos para establecer, obtener acceso y recuperar el delegado del controlador de eventos basándose en la clave del evento.</span><span class="sxs-lookup"><span data-stu-id="04dd1-110">The collection class must provide methods for setting, accessing, and retrieving the event handler delegate based on the event key.</span></span> <span data-ttu-id="04dd1-111">Por ejemplo, se puede utilizar una clase <xref:System.Collections.Hashtable> o derivar una clase personalizada a partir de la clase <xref:System.Collections.DictionaryBase>.</span><span class="sxs-lookup"><span data-stu-id="04dd1-111">For example, you could use a <xref:System.Collections.Hashtable> class, or derive a custom class from the <xref:System.Collections.DictionaryBase> class.</span></span> <span data-ttu-id="04dd1-112">No es necesario exponer los detalles de implementación de la colección de delegados fuera de la clase.</span><span class="sxs-lookup"><span data-stu-id="04dd1-112">The implementation details of the delegate collection do not need to be exposed outside your class.</span></span>  
  
 <span data-ttu-id="04dd1-113">Cada una de las propiedades de evento de la clase define un método de descriptor de acceso add y un método de descriptor de acceso remove.</span><span class="sxs-lookup"><span data-stu-id="04dd1-113">Each event property within the class defines an add accessor method and a remove accessor method.</span></span> <span data-ttu-id="04dd1-114">El descriptor de acceso add de una propiedad de evento agrega la instancia de delegado de entrada a la colección de delegados.</span><span class="sxs-lookup"><span data-stu-id="04dd1-114">The add accessor for an event property adds the input delegate instance to the delegate collection.</span></span> <span data-ttu-id="04dd1-115">El descriptor de acceso remove de una propiedad de evento quita la instancia de delegado de entrada de la colección de delegados.</span><span class="sxs-lookup"><span data-stu-id="04dd1-115">The remove accessor for an event property removes the input delegate instance from the delegate collection.</span></span> <span data-ttu-id="04dd1-116">Los descriptores de acceso de las propiedades de eventos utilizan la clave predefinida de la propiedad de evento para agregar y quitar instancias en la colección de delegados.</span><span class="sxs-lookup"><span data-stu-id="04dd1-116">The event property accessors use the predefined key for the event property to add and remove instances from the delegate collection.</span></span>  
  
### <a name="to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="04dd1-117">Para controlar varios eventos mediante las propiedades de evento</span><span class="sxs-lookup"><span data-stu-id="04dd1-117">To handle multiple events using event properties</span></span>  
  
1. <span data-ttu-id="04dd1-118">Defina una colección de delegados dentro de la clase que provoca los eventos.</span><span class="sxs-lookup"><span data-stu-id="04dd1-118">Define a delegate collection within the class that raises the events.</span></span>  
  
2. <span data-ttu-id="04dd1-119">Defina una clave para cada evento.</span><span class="sxs-lookup"><span data-stu-id="04dd1-119">Define a key for each event.</span></span>  
  
3. <span data-ttu-id="04dd1-120">Defina las propiedades de evento de la clase que provoca los eventos.</span><span class="sxs-lookup"><span data-stu-id="04dd1-120">Define the event properties in the class that raises the events.</span></span>  
  
4. <span data-ttu-id="04dd1-121">Utilice la colección de delegados para implementar los métodos de descriptor de acceso add y remove de las propiedades de evento.</span><span class="sxs-lookup"><span data-stu-id="04dd1-121">Use the delegate collection to implement the add and remove accessor methods for the event properties.</span></span>  
  
5. <span data-ttu-id="04dd1-122">Utilice las propiedades de evento públicas para agregar y quitar delegados de controlador de eventos en las clases que controlan los eventos.</span><span class="sxs-lookup"><span data-stu-id="04dd1-122">Use the public event properties to add and remove event handler delegates in the classes that handle the events.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04dd1-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04dd1-123">Example</span></span>  

 <span data-ttu-id="04dd1-124">En el siguiente ejemplo de C#, se implementan las propiedades de evento `MouseDown` y `MouseUp` mediante el uso de <xref:System.ComponentModel.EventHandlerList> para almacenar el delegado de cada evento.</span><span class="sxs-lookup"><span data-stu-id="04dd1-124">The following C# example implements the event properties `MouseDown` and `MouseUp`, using an <xref:System.ComponentModel.EventHandlerList> to store each event's delegate.</span></span> <span data-ttu-id="04dd1-125">Las palabras clave de las construcciones de propiedades de evento están en negrita.</span><span class="sxs-lookup"><span data-stu-id="04dd1-125">The keywords of the event property constructs are in bold type.</span></span>  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="04dd1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="04dd1-126">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [<span data-ttu-id="04dd1-127">Eventos</span><span class="sxs-lookup"><span data-stu-id="04dd1-127">Events</span></span>](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [<span data-ttu-id="04dd1-128">Cómo: Declarar eventos personalizados para conservar memoria</span><span class="sxs-lookup"><span data-stu-id="04dd1-128">How to: Declare Custom Events To Conserve Memory</span></span>](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
