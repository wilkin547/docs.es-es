---
title: 'Procedimiento Implementar eventos de interfaz: Guía de programación de C#'
description: Aprenda a implementar eventos de interfaz en una clase. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 153a2efa254bf2f2c81cec4b28a53207cdc4efe5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167553"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="e570c-104">Procedimiento Implementar eventos de interfaz (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e570c-104">How to implement interface events (C# Programming Guide)</span></span>

<span data-ttu-id="e570c-105">Un [interfaz](../../language-reference/keywords/interface.md) puede declarar un [evento](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="e570c-105">An [interface](../../language-reference/keywords/interface.md) can declare an [event](../../language-reference/keywords/event.md).</span></span> <span data-ttu-id="e570c-106">En el siguiente ejemplo, se muestra cómo implementar eventos de interfaz en una clase.</span><span class="sxs-lookup"><span data-stu-id="e570c-106">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="e570c-107">Básicamente, las reglas son las mismas que para implementar cualquier propiedad o método de interfaz.</span><span class="sxs-lookup"><span data-stu-id="e570c-107">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="e570c-108">Para implementar eventos de interfaz en una clase</span><span class="sxs-lookup"><span data-stu-id="e570c-108">To implement interface events in a class</span></span>  
  
<span data-ttu-id="e570c-109">Declare el evento en la clase y, después, invóquelo en las áreas apropiadas.</span><span class="sxs-lookup"><span data-stu-id="e570c-109">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a><span data-ttu-id="e570c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e570c-110">Example</span></span>  

<span data-ttu-id="e570c-111">En el ejemplo siguiente se muestra cómo controlar la situación menos común en que la clase hereda de dos o más interfaces y cada interfaz tiene un evento con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="e570c-111">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="e570c-112">En esta situación, debe proporcionar una implementación de interfaz explícita para uno de los eventos como mínimo.</span><span class="sxs-lookup"><span data-stu-id="e570c-112">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="e570c-113">Al escribir una implementación de interfaz explícita para un evento, también debe escribir los descriptores de acceso del evento `add` y `remove`.</span><span class="sxs-lookup"><span data-stu-id="e570c-113">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="e570c-114">Normalmente, los proporciona el compilador, pero en este caso no es posible.</span><span class="sxs-lookup"><span data-stu-id="e570c-114">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="e570c-115">Al proporcionar sus propios descriptores de acceso, puede especificar si los dos eventos se representan mediante el mismo evento en la clase o mediante eventos diferentes.</span><span class="sxs-lookup"><span data-stu-id="e570c-115">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="e570c-116">Por ejemplo, si los eventos deben provocarse en momentos diferentes según las especificaciones de la interfaz, puede asociar cada evento a una implementación distinta en su clase.</span><span class="sxs-lookup"><span data-stu-id="e570c-116">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="e570c-117">En el ejemplo siguiente, los suscriptores determinan qué evento `OnDraw` recibirán al convertir la referencia de forma en `IShape` o en `IDrawingObject`.</span><span class="sxs-lookup"><span data-stu-id="e570c-117">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="e570c-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e570c-118">See also</span></span>

- [<span data-ttu-id="e570c-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e570c-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e570c-120">Eventos</span><span class="sxs-lookup"><span data-stu-id="e570c-120">Events</span></span>](./index.md)
- [<span data-ttu-id="e570c-121">Delegados</span><span class="sxs-lookup"><span data-stu-id="e570c-121">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="e570c-122">Implementación de interfaz explícita</span><span class="sxs-lookup"><span data-stu-id="e570c-122">Explicit Interface Implementation</span></span>](../interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="e570c-123">Procedimiento para generar eventos de una clase base en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="e570c-123">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)
