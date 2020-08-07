---
title: 'Procedimiento Producir eventos de una clase base en clases derivadas: Guía de programación de C#'
description: Aprenda a generar eventos de una clase base en clases derivadas. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: b0b0a16a1fd165e437fc79ccacb20d406f5cff63
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302105"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="4511f-104">Procedimiento Producir eventos de una clase base en clases derivadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4511f-104">How to raise base class events in derived classes (C# Programming Guide)</span></span>
<span data-ttu-id="4511f-105">En el siguiente ejemplo sencillo se muestra la forma estándar de declarar eventos en una clase base para que también se puedan generar desde clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="4511f-105">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="4511f-106">Este patrón se usa mucho en las clases de Windows Forms de las bibliotecas de clases de .NET.</span><span class="sxs-lookup"><span data-stu-id="4511f-106">This pattern is used extensively in Windows Forms classes in the .NET class libraries.</span></span>  
  
 <span data-ttu-id="4511f-107">Al crear una clase que se pueda usar como clase base para otras clases, debe considerar el hecho de que los eventos son un tipo especial de delegado que solo se pueden invocar desde la clase que los haya declarado.</span><span class="sxs-lookup"><span data-stu-id="4511f-107">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="4511f-108">Las clases derivadas no pueden invocar directamente a eventos declarados en la clase base.</span><span class="sxs-lookup"><span data-stu-id="4511f-108">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="4511f-109">Aunque a veces pueda querer un evento que solo la clase base pueda generar, en la mayoría de los casos debería habilitar la clase derivada para invocar a eventos de clase base.</span><span class="sxs-lookup"><span data-stu-id="4511f-109">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="4511f-110">Para ello, puede crear un método de invocación protegido en la clase base que encapsula el evento.</span><span class="sxs-lookup"><span data-stu-id="4511f-110">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="4511f-111">Al llamar o invalidar a este método de invocación, las clases derivadas pueden invocar directamente al evento.</span><span class="sxs-lookup"><span data-stu-id="4511f-111">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4511f-112">No declare eventos virtuales en una clase base y los invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="4511f-112">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="4511f-113">El compilador de C# no los controla correctamente y no es posible decir si un suscriptor del evento derivado se está suscribiendo realmente al evento de clase base.</span><span class="sxs-lookup"><span data-stu-id="4511f-113">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4511f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4511f-114">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4511f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4511f-115">See also</span></span>

- [<span data-ttu-id="4511f-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4511f-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4511f-117">Eventos</span><span class="sxs-lookup"><span data-stu-id="4511f-117">Events</span></span>](./index.md)
- [<span data-ttu-id="4511f-118">Delegados</span><span class="sxs-lookup"><span data-stu-id="4511f-118">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="4511f-119">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="4511f-119">Access Modifiers</span></span>](../classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="4511f-120">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4511f-120">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
