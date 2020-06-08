---
title: 'Cómo: Controlar varios eventos mediante propiedades de eventos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: c5be541c1a40c5d16a0502e76adef24f6a41cc89
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288477"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="6bcbb-102">Cómo: Controlar varios eventos mediante propiedades de eventos</span><span class="sxs-lookup"><span data-stu-id="6bcbb-102">How to: Handle Multiple Events Using Event Properties</span></span>
<span data-ttu-id="6bcbb-103">Para poder utilizar propiedades de evento, hay que definirlas en la clase que provoca los eventos y, a continuación, establecer los delegados de las propiedades de evento en las clases que controlan los eventos.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-103">To use event properties, you define the event properties in the class that raises the events, and then set the delegates for the event properties in classes that handle the events.</span></span> <span data-ttu-id="6bcbb-104">Para implementar varias propiedades de evento en una clase, esta clase deberá almacenar internamente y mantener el delegado definido para cada evento.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-104">To implement multiple event properties in a class, the class must internally store and maintain the delegate defined for each event.</span></span> <span data-ttu-id="6bcbb-105">Para hacerlo, uno de los enfoques típicos consiste en implementar una colección de delegados que se indice por medio de una clave de evento.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-105">A typical approach is to implement a delegate collection that is indexed by an event key.</span></span>  
  
 <span data-ttu-id="6bcbb-106">Para almacenar los delegados de cada evento, puede utilizar la clase <xref:System.ComponentModel.EventHandlerList> o implementar su propia colección.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-106">To store the delegates for each event, you can use the <xref:System.ComponentModel.EventHandlerList> class, or implement your own collection.</span></span> <span data-ttu-id="6bcbb-107">La clase de colección debe proporcionar métodos para establecer, obtener acceso y recuperar el delegado del controlador de eventos basándose en la clave del evento.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-107">The collection class must provide methods for setting, accessing, and retrieving the event handler delegate based on the event key.</span></span> <span data-ttu-id="6bcbb-108">Por ejemplo, se puede utilizar una clase <xref:System.Collections.Hashtable> o derivar una clase personalizada a partir de la clase <xref:System.Collections.DictionaryBase>.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-108">For example, you could use a <xref:System.Collections.Hashtable> class, or derive a custom class from the <xref:System.Collections.DictionaryBase> class.</span></span> <span data-ttu-id="6bcbb-109">No es necesario exponer los detalles de implementación de la colección de delegados fuera de la clase.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-109">The implementation details of the delegate collection do not need to be exposed outside your class.</span></span>  
  
 <span data-ttu-id="6bcbb-110">Cada una de las propiedades de evento de la clase define un método de descriptor de acceso add y un método de descriptor de acceso remove.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-110">Each event property within the class defines an add accessor method and a remove accessor method.</span></span> <span data-ttu-id="6bcbb-111">El descriptor de acceso add de una propiedad de evento agrega la instancia de delegado de entrada a la colección de delegados.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-111">The add accessor for an event property adds the input delegate instance to the delegate collection.</span></span> <span data-ttu-id="6bcbb-112">El descriptor de acceso remove de una propiedad de evento quita la instancia de delegado de entrada de la colección de delegados.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-112">The remove accessor for an event property removes the input delegate instance from the delegate collection.</span></span> <span data-ttu-id="6bcbb-113">Los descriptores de acceso de las propiedades de eventos utilizan la clave predefinida de la propiedad de evento para agregar y quitar instancias en la colección de delegados.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-113">The event property accessors use the predefined key for the event property to add and remove instances from the delegate collection.</span></span>  
  
### <a name="to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="6bcbb-114">Para controlar varios eventos mediante las propiedades de evento</span><span class="sxs-lookup"><span data-stu-id="6bcbb-114">To handle multiple events using event properties</span></span>  
  
1. <span data-ttu-id="6bcbb-115">Defina una colección de delegados dentro de la clase que provoca los eventos.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-115">Define a delegate collection within the class that raises the events.</span></span>  
  
2. <span data-ttu-id="6bcbb-116">Defina una clave para cada evento.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-116">Define a key for each event.</span></span>  
  
3. <span data-ttu-id="6bcbb-117">Defina las propiedades de evento de la clase que provoca los eventos.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-117">Define the event properties in the class that raises the events.</span></span>  
  
4. <span data-ttu-id="6bcbb-118">Utilice la colección de delegados para implementar los métodos de descriptor de acceso add y remove de las propiedades de evento.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-118">Use the delegate collection to implement the add and remove accessor methods for the event properties.</span></span>  
  
5. <span data-ttu-id="6bcbb-119">Utilice las propiedades de evento públicas para agregar y quitar delegados de controlador de eventos en las clases que controlan los eventos.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-119">Use the public event properties to add and remove event handler delegates in the classes that handle the events.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bcbb-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6bcbb-120">Example</span></span>  
 <span data-ttu-id="6bcbb-121">En el siguiente ejemplo de C#, se implementan las propiedades de evento `MouseDown` y `MouseUp` mediante el uso de <xref:System.ComponentModel.EventHandlerList> para almacenar el delegado de cada evento.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-121">The following C# example implements the event properties `MouseDown` and `MouseUp`, using an <xref:System.ComponentModel.EventHandlerList> to store each event's delegate.</span></span> <span data-ttu-id="6bcbb-122">Las palabras clave de las construcciones de propiedades de evento están en negrita.</span><span class="sxs-lookup"><span data-stu-id="6bcbb-122">The keywords of the event property constructs are in bold type.</span></span>  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="6bcbb-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bcbb-123">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [<span data-ttu-id="6bcbb-124">Eventos</span><span class="sxs-lookup"><span data-stu-id="6bcbb-124">Events</span></span>](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6bcbb-125">Declarar eventos personalizados para conservar memoria</span><span class="sxs-lookup"><span data-stu-id="6bcbb-125">How to: Declare Custom Events To Conserve Memory</span></span>](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
