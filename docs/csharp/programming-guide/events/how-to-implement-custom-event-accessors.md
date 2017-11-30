---
title: "Cómo: Implementar descriptores de acceso de eventos personalizados (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3ff5fedeeaa427bb62991f9b406c167647dc376d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="5ef7a-102">Cómo: Implementar descriptores de acceso de eventos personalizados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5ef7a-102">How to: Implement Custom Event Accessors (C# Programming Guide)</span></span>
<span data-ttu-id="5ef7a-103">Un evento es un tipo especial de delegado de multidifusión que solo puede invocarse desde dentro de la clase en la que se declara.</span><span class="sxs-lookup"><span data-stu-id="5ef7a-103">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="5ef7a-104">El código cliente se suscribe al evento proporcionando una referencia a un método que debería invocarse cuando se desencadena el evento.</span><span class="sxs-lookup"><span data-stu-id="5ef7a-104">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="5ef7a-105">Estos métodos se agregan a la lista de invocación del delegado a través de descriptores de acceso de eventos, que son similares a los descriptores de acceso de propiedad, con la diferencia de que los descriptores de acceso de eventos se denominan `add` y `remove`.</span><span class="sxs-lookup"><span data-stu-id="5ef7a-105">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="5ef7a-106">En la mayoría de los casos, no tiene que proporcionar descriptores de acceso de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5ef7a-106">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="5ef7a-107">Cuando no proporciona ningún descriptor de acceso de eventos personalizado en el código, el compilador los agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5ef7a-107">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="5ef7a-108">En cambio, en algunos casos puede que tenga que proporcionar un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="5ef7a-108">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="5ef7a-109">Uno de estos casos se muestra en el tema [Cómo: Implementar eventos de interfaz](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="5ef7a-109">One such case is shown in the topic [How to:  Implement Interface Events](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ef7a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ef7a-110">Example</span></span>  
 <span data-ttu-id="5ef7a-111">En el ejemplo siguiente se muestra cómo implementar descriptores de acceso de eventos add y remove personalizados.</span><span class="sxs-lookup"><span data-stu-id="5ef7a-111">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="5ef7a-112">Aunque puede sustituir cualquier código dentro de los descriptores de acceso, recomendamos que bloquee el evento antes de agregar o quitar un nuevo método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="5ef7a-112">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
```  
event EventHandler IDrawingObject.OnDraw  
        {  
            add  
            {  
                lock (PreDrawEvent)  
                {  
                    PreDrawEvent += value;  
                }  
            }  
            remove  
            {  
                lock (PreDrawEvent)  
                {  
                    PreDrawEvent -= value;  
                }  
            }  
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ef7a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ef7a-113">See Also</span></span>  
 [<span data-ttu-id="5ef7a-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="5ef7a-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="5ef7a-115">event</span><span class="sxs-lookup"><span data-stu-id="5ef7a-115">event</span></span>](../../../csharp/language-reference/keywords/event.md)
