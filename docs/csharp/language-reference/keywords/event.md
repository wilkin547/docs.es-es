---
title: event (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
dev_langs:
- CSharp
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 674e36625a68243afff75f6c5028309dc7aff02a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="event-c-reference"></a><span data-ttu-id="22340-102">event (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="22340-102">event (C# Reference)</span></span>
<span data-ttu-id="22340-103">La palabra clave `event` se usa para declarar un evento en una clase de publicador.</span><span class="sxs-lookup"><span data-stu-id="22340-103">The `event` keyword is used to declare an event in a publisher class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22340-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22340-104">Example</span></span>  
 <span data-ttu-id="22340-105">En el ejemplo siguiente se muestra cómo declarar y generar un evento que usa <xref:System.EventHandler> como el tipo de delegado subyacente.</span><span class="sxs-lookup"><span data-stu-id="22340-105">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="22340-106">Para obtener el código de ejemplo completo que también muestra cómo usar el tipo delegado <xref:System.EventHandler%601> genérico y cómo suscribirse a un evento y crear un método de controlador de evento, vea [Cómo: Publicar eventos que cumplan las directrices de .NET Framework (Guía de programación de C#)](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="22340-106">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to: Publish Events that Conform to .NET Framework Guidelines](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>  
  
 <span data-ttu-id="22340-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="22340-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span></span>  
  
 <span data-ttu-id="22340-108">Los eventos son un tipo especial de delegado de multidifusión que solo se pueden invocar desde la clase o el struct en la que se declaran (la clase de publicador).</span><span class="sxs-lookup"><span data-stu-id="22340-108">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="22340-109">Si otras clases o structs se suscriben al evento, se llamará a sus métodos de controlador de eventos cuando la clase de publicador genera el evento.</span><span class="sxs-lookup"><span data-stu-id="22340-109">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="22340-110">Para más información y ejemplos de código, vea [Eventos](../../../csharp/programming-guide/events/index.md) y [Delegados](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="22340-110">For more information and code examples, see [Events](../../../csharp/programming-guide/events/index.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
 <span data-ttu-id="22340-111">Los eventos se pueden marcar como [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="22340-111">Events can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="22340-112">Estos modificadores de acceso definen cómo los usuarios de la clase pueden obtener acceso al evento.</span><span class="sxs-lookup"><span data-stu-id="22340-112">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="22340-113">Para obtener más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="22340-113">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="keywords-and-events"></a><span data-ttu-id="22340-114">Palabras clave y eventos</span><span class="sxs-lookup"><span data-stu-id="22340-114">Keywords and Events</span></span>  
 <span data-ttu-id="22340-115">Las palabras clave siguientes se aplican a eventos.</span><span class="sxs-lookup"><span data-stu-id="22340-115">The following keywords apply to events.</span></span>  
  
|<span data-ttu-id="22340-116">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="22340-116">Keyword</span></span>|<span data-ttu-id="22340-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="22340-117">Description</span></span>|<span data-ttu-id="22340-118">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="22340-118">For more information</span></span>|  
|-------------|-----------------|--------------------------|  
|[<span data-ttu-id="22340-119">static</span><span class="sxs-lookup"><span data-stu-id="22340-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="22340-120">Hace que el evento esté disponible para los llamadores en cualquier momento, aunque no exista ninguna instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="22340-120">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="22340-121">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="22340-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[<span data-ttu-id="22340-122">virtual</span><span class="sxs-lookup"><span data-stu-id="22340-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="22340-123">Permite que las clases derivadas invaliden el comportamiento de eventos mediante la palabra clave [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="22340-123">Allows derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span>|[<span data-ttu-id="22340-124">Herencia</span><span class="sxs-lookup"><span data-stu-id="22340-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[<span data-ttu-id="22340-125">sealed</span><span class="sxs-lookup"><span data-stu-id="22340-125">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="22340-126">Especifica que ya no es virtual para las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="22340-126">Specifies that for derived classes it is no longer virtual.</span></span>||  
|[<span data-ttu-id="22340-127">abstract</span><span class="sxs-lookup"><span data-stu-id="22340-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="22340-128">El compilador no generará los bloques de descriptor de acceso de eventos `add` y `remove`, y por tanto, las clases deben proporcionar su propia implementación.</span><span class="sxs-lookup"><span data-stu-id="22340-128">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||  
  
 <span data-ttu-id="22340-129">Un evento puede declararse como evento estático mediante la palabra clave [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="22340-129">An event may be declared as a static event by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="22340-130">Esto hace que el evento esté disponible para los llamadores en cualquier momento, aunque no exista ninguna instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="22340-130">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="22340-131">Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="22340-131">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="22340-132">Un evento puede marcarse como virtual mediante la palabra clave [virtual](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="22340-132">An event can be marked as a virtual event by using the [virtual](../../../csharp/language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="22340-133">Esto permite que las clases derivadas invaliden el comportamiento de eventos mediante la palabra clave [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="22340-133">This enables derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="22340-134">Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="22340-134">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="22340-135">Un evento que reemplaza un evento virtual también puede ser [sealed](../../../csharp/language-reference/keywords/sealed.md), que especifica que ya no es virtual para las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="22340-135">An event overriding a virtual event can also be [sealed](../../../csharp/language-reference/keywords/sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="22340-136">Por último, se puede declarar un evento como [abstract](../../../csharp/language-reference/keywords/abstract.md), lo que significa que el compilador no generará los bloques de descriptor de acceso de eventos `add` y `remove`.</span><span class="sxs-lookup"><span data-stu-id="22340-136">Lastly, an event can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="22340-137">Por tanto, las clases derivadas deben proporcionar una implementación propia.</span><span class="sxs-lookup"><span data-stu-id="22340-137">Therefore derived classes must provide their own implementation.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="22340-138">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="22340-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22340-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="22340-139">See Also</span></span>  
 <span data-ttu-id="22340-140">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="22340-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="22340-141">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="22340-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="22340-142">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="22340-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="22340-143">[add](../../../csharp/language-reference/keywords/add.md) </span><span class="sxs-lookup"><span data-stu-id="22340-143">[add](../../../csharp/language-reference/keywords/add.md) </span></span>  
 <span data-ttu-id="22340-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span><span class="sxs-lookup"><span data-stu-id="22340-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span></span>  
 <span data-ttu-id="22340-145">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="22340-145">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="22340-146">Cómo: Combinar delegados (delegados de multidifusión)</span><span class="sxs-lookup"><span data-stu-id="22340-146">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

