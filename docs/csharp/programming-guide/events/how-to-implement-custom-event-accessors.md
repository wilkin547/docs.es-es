---
title: 'Procedimiento Implementar descriptores de acceso de eventos personalizados: Guía de programación de C#'
description: Aprenda a implementar descriptores de acceso de eventos personalizados. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 4094aa1fedbceb68790b484608b3ea0ebc1e5cf6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302144"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="03dd6-104">Procedimiento Implementar descriptores de acceso de eventos personalizados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="03dd6-104">How to implement custom event accessors (C# Programming Guide)</span></span>
<span data-ttu-id="03dd6-105">Un evento es un tipo especial de delegado de multidifusión que solo puede invocarse desde dentro de la clase en la que se declara.</span><span class="sxs-lookup"><span data-stu-id="03dd6-105">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="03dd6-106">El código cliente se suscribe al evento proporcionando una referencia a un método que debería invocarse cuando se desencadena el evento.</span><span class="sxs-lookup"><span data-stu-id="03dd6-106">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="03dd6-107">Estos métodos se agregan a la lista de invocación del delegado a través de descriptores de acceso de eventos, que son similares a los descriptores de acceso de propiedad, con la diferencia de que los descriptores de acceso de eventos se denominan `add` y `remove`.</span><span class="sxs-lookup"><span data-stu-id="03dd6-107">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="03dd6-108">En la mayoría de los casos, no tiene que proporcionar descriptores de acceso de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="03dd6-108">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="03dd6-109">Cuando no proporciona ningún descriptor de acceso de eventos personalizado en el código, el compilador los agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="03dd6-109">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="03dd6-110">En cambio, en algunos casos puede que tenga que proporcionar un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="03dd6-110">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="03dd6-111">Uno de estos casos se muestra en el tema [Procedimiento Implementar eventos de interfaz](./how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="03dd6-111">One such case is shown in the topic [How to implement interface events](./how-to-implement-interface-events.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="03dd6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03dd6-112">Example</span></span>  
 <span data-ttu-id="03dd6-113">En el ejemplo siguiente se muestra cómo implementar descriptores de acceso de eventos add y remove personalizados.</span><span class="sxs-lookup"><span data-stu-id="03dd6-113">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="03dd6-114">Aunque puede sustituir cualquier código dentro de los descriptores de acceso, recomendamos que bloquee el evento antes de agregar o quitar un nuevo método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="03dd6-114">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="03dd6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="03dd6-115">See also</span></span>

- [<span data-ttu-id="03dd6-116">Eventos</span><span class="sxs-lookup"><span data-stu-id="03dd6-116">Events</span></span>](./index.md)
- [<span data-ttu-id="03dd6-117">event</span><span class="sxs-lookup"><span data-stu-id="03dd6-117">event</span></span>](../../language-reference/keywords/event.md)
