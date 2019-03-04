---
title: 'Procedimiento Producir eventos de una clase base en clases derivadas: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: bc968ea9c6f60ea6efda807bf254f595c61f8d4a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976088"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="e9783-102">Procedimiento Producir eventos de una clase base en clases derivadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e9783-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="e9783-103">En el siguiente ejemplo sencillo se muestra la forma estándar de declarar eventos en una clase base para que también se puedan generar desde clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="e9783-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="e9783-104">Este patrón se usa mucho en las clases de Windows Forms de la biblioteca de clases de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9783-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="e9783-105">Al crear una clase que se pueda usar como clase base para otras clases, debe considerar el hecho de que los eventos son un tipo especial de delegado que solo se pueden invocar desde la clase que los haya declarado.</span><span class="sxs-lookup"><span data-stu-id="e9783-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="e9783-106">Las clases derivadas no pueden invocar directamente a eventos declarados en la clase base.</span><span class="sxs-lookup"><span data-stu-id="e9783-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="e9783-107">Aunque a veces pueda querer un evento que solo la clase base pueda generar, en la mayoría de los casos debería habilitar la clase derivada para invocar a eventos de clase base.</span><span class="sxs-lookup"><span data-stu-id="e9783-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="e9783-108">Para ello, puede crear un método de invocación protegido en la clase base que encapsula el evento.</span><span class="sxs-lookup"><span data-stu-id="e9783-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="e9783-109">Al llamar o invalidar a este método de invocación, las clases derivadas pueden invocar directamente al evento.</span><span class="sxs-lookup"><span data-stu-id="e9783-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9783-110">No declare eventos virtuales en una clase base y los invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="e9783-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="e9783-111">El compilador de C# no los controla correctamente y no es posible decir si un suscriptor del evento derivado se está suscribiendo realmente al evento de clase base.</span><span class="sxs-lookup"><span data-stu-id="e9783-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9783-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9783-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e9783-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9783-113">See also</span></span>

- [<span data-ttu-id="e9783-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e9783-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e9783-115">Eventos</span><span class="sxs-lookup"><span data-stu-id="e9783-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="e9783-116">Delegados</span><span class="sxs-lookup"><span data-stu-id="e9783-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="e9783-117">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="e9783-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="e9783-118">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9783-118">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
