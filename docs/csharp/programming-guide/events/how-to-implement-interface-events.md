---
title: 'Procedimiento Implementar eventos de interfaz: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: b84b96245310bce557bcd3865e41cf152e7ae9df
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712343"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="00eb6-102">Procedimiento Implementar eventos de interfaz (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="00eb6-102">How to implement interface events (C# Programming Guide)</span></span>
<span data-ttu-id="00eb6-103">Un [interfaz](../../language-reference/keywords/interface.md) puede declarar un [evento](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="00eb6-103">An [interface](../../language-reference/keywords/interface.md) can declare an [event](../../language-reference/keywords/event.md).</span></span> <span data-ttu-id="00eb6-104">En el siguiente ejemplo, se muestra cómo implementar eventos de interfaz en una clase.</span><span class="sxs-lookup"><span data-stu-id="00eb6-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="00eb6-105">Básicamente, las reglas son las mismas que para implementar cualquier propiedad o método de interfaz.</span><span class="sxs-lookup"><span data-stu-id="00eb6-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="00eb6-106">Para implementar eventos de interfaz en una clase</span><span class="sxs-lookup"><span data-stu-id="00eb6-106">To implement interface events in a class</span></span>  
  
<span data-ttu-id="00eb6-107">Declare el evento en la clase y, después, invóquelo en las áreas apropiadas.</span><span class="sxs-lookup"><span data-stu-id="00eb6-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="00eb6-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00eb6-108">Example</span></span>  
<span data-ttu-id="00eb6-109">En el ejemplo siguiente se muestra cómo controlar la situación menos común en que la clase hereda de dos o más interfaces y cada interfaz tiene un evento con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="00eb6-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="00eb6-110">En esta situación, debe proporcionar una implementación de interfaz explícita para uno de los eventos como mínimo.</span><span class="sxs-lookup"><span data-stu-id="00eb6-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="00eb6-111">Al escribir una implementación de interfaz explícita para un evento, también debe escribir los descriptores de acceso del evento `add` y `remove`.</span><span class="sxs-lookup"><span data-stu-id="00eb6-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="00eb6-112">Normalmente, los proporciona el compilador, pero en este caso no es posible.</span><span class="sxs-lookup"><span data-stu-id="00eb6-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="00eb6-113">Al proporcionar sus propios descriptores de acceso, puede especificar si los dos eventos se representan mediante el mismo evento en la clase o mediante eventos diferentes.</span><span class="sxs-lookup"><span data-stu-id="00eb6-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="00eb6-114">Por ejemplo, si los eventos deben provocarse en momentos diferentes según las especificaciones de la interfaz, puede asociar cada evento a una implementación distinta en su clase.</span><span class="sxs-lookup"><span data-stu-id="00eb6-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="00eb6-115">En el ejemplo siguiente, los suscriptores determinan qué evento `OnDraw` recibirán al convertir la referencia de forma en `IShape` o en `IDrawingObject`.</span><span class="sxs-lookup"><span data-stu-id="00eb6-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="00eb6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="00eb6-116">See also</span></span>

- [<span data-ttu-id="00eb6-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="00eb6-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="00eb6-118">Eventos</span><span class="sxs-lookup"><span data-stu-id="00eb6-118">Events</span></span>](./index.md)
- [<span data-ttu-id="00eb6-119">Delegados</span><span class="sxs-lookup"><span data-stu-id="00eb6-119">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="00eb6-120">Implementación de interfaz explícita</span><span class="sxs-lookup"><span data-stu-id="00eb6-120">Explicit Interface Implementation</span></span>](../interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="00eb6-121">Procedimiento para generar eventos de una clase base en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="00eb6-121">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)
