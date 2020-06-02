---
title: Diseño de eventos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: 852c99b1a41691911f7ae82d3b8104526811757d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289829"
---
# <a name="event-design"></a><span data-ttu-id="a7afe-102">Diseño de eventos</span><span class="sxs-lookup"><span data-stu-id="a7afe-102">Event Design</span></span>
<span data-ttu-id="a7afe-103">Los eventos son la forma de devoluciones de llamada que se usa con más frecuencia (construcciones que permiten al marco de trabajo llamar a código de usuario).</span><span class="sxs-lookup"><span data-stu-id="a7afe-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="a7afe-104">Otros mecanismos de devolución de llamada incluyen miembros que toman delegados, miembros virtuales y complementos basados en interfaz. los datos de los estudios de facilidad de uso indican que la mayoría de los desarrolladores se sienten más cómodos con eventos que si usan los otros mecanismos de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a7afe-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="a7afe-105">Los eventos se integran perfectamente con Visual Studio y muchos lenguajes.</span><span class="sxs-lookup"><span data-stu-id="a7afe-105">Events are nicely integrated with Visual Studio and many languages.</span></span>

 <span data-ttu-id="a7afe-106">Es importante tener en cuenta que hay dos grupos de eventos: los eventos que se generan antes de que cambie un estado del sistema, denominados eventos previos, y eventos generados después de un cambio de estado, denominados eventos posteriores.</span><span class="sxs-lookup"><span data-stu-id="a7afe-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="a7afe-107">Un ejemplo de evento anterior sería `Form.Closing` , que se desencadena antes de que se cierre un formulario.</span><span class="sxs-lookup"><span data-stu-id="a7afe-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="a7afe-108">Un ejemplo de evento posterior sería `Form.Closed` , que se genera después de cerrar un formulario.</span><span class="sxs-lookup"><span data-stu-id="a7afe-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>

 <span data-ttu-id="a7afe-109">✔️ usar el término "raise" para los eventos en lugar de "Fire" o "Trigger".</span><span class="sxs-lookup"><span data-stu-id="a7afe-109">✔️ DO use the term "raise" for events rather than "fire" or "trigger."</span></span>

 <span data-ttu-id="a7afe-110">✔️ usar en <xref:System.EventHandler%601?displayProperty=nameWithType> lugar de crear manualmente nuevos delegados que se usarán como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-110">✔️ DO use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>

 <span data-ttu-id="a7afe-111">✔️ considere la posibilidad de usar una subclase de <xref:System.EventArgs> como argumento de evento, a menos que esté absolutamente seguro de que el evento nunca tendrá que llevar ningún dato al método de control de eventos, en cuyo caso puede utilizar el `EventArgs` tipo directamente.</span><span class="sxs-lookup"><span data-stu-id="a7afe-111">✔️ CONSIDER using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>

 <span data-ttu-id="a7afe-112">Si envía una API `EventArgs` directamente, nunca podrá agregar ningún dato que se lleve a cabo con el evento sin interrumpir la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="a7afe-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="a7afe-113">Si utiliza una subclase, incluso si inicialmente está completamente vacía, podrá agregar propiedades a la subclase cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a7afe-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>

 <span data-ttu-id="a7afe-114">✔️ usar un método virtual protegido para generar cada evento.</span><span class="sxs-lookup"><span data-stu-id="a7afe-114">✔️ DO use a protected virtual method to raise each event.</span></span> <span data-ttu-id="a7afe-115">Esto solo se aplica a eventos no estáticos en clases no selladas, no en Structs, clases selladas ni eventos estáticos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>

 <span data-ttu-id="a7afe-116">El propósito del método es proporcionar una manera para que una clase derivada controle el evento mediante una invalidación.</span><span class="sxs-lookup"><span data-stu-id="a7afe-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="a7afe-117">Reemplazar es una forma más flexible, más rápida y más natural de controlar eventos de clase base en clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="a7afe-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="a7afe-118">Por Convención, el nombre del método debe empezar por "ON" y debe ir seguido del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="a7afe-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>

 <span data-ttu-id="a7afe-119">La clase derivada puede elegir no llamar a la implementación base del método en su invalidación.</span><span class="sxs-lookup"><span data-stu-id="a7afe-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="a7afe-120">Para ello, no incluya ningún procesamiento en el método necesario para que la clase base funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7afe-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>

 <span data-ttu-id="a7afe-121">✔️ realizar un parámetro al método protegido que genera un evento.</span><span class="sxs-lookup"><span data-stu-id="a7afe-121">✔️ DO take one parameter to the protected method that raises an event.</span></span>

 <span data-ttu-id="a7afe-122">El parámetro debe tener el nombre `e` y debe escribirse como la clase de argumento de evento.</span><span class="sxs-lookup"><span data-stu-id="a7afe-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>

 <span data-ttu-id="a7afe-123">❌NO pase NULL como remitente al generar un evento no estático.</span><span class="sxs-lookup"><span data-stu-id="a7afe-123">❌ DO NOT pass null as the sender when raising a nonstatic event.</span></span>

 <span data-ttu-id="a7afe-124">✔️ pasar null como remitente al generar un evento estático.</span><span class="sxs-lookup"><span data-stu-id="a7afe-124">✔️ DO pass null as the sender when raising a static event.</span></span>

 <span data-ttu-id="a7afe-125">❌NO pase NULL como parámetro de datos de evento al generar un evento.</span><span class="sxs-lookup"><span data-stu-id="a7afe-125">❌ DO NOT pass null as the event data parameter when raising an event.</span></span>

 <span data-ttu-id="a7afe-126">Debe pasar `EventArgs.Empty` si no desea pasar datos al método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="a7afe-127">Los desarrolladores esperan que este parámetro no sea NULL.</span><span class="sxs-lookup"><span data-stu-id="a7afe-127">Developers expect this parameter not to be null.</span></span>

 <span data-ttu-id="a7afe-128">✔️ considere la posibilidad de generar eventos que el usuario final pueda cancelar.</span><span class="sxs-lookup"><span data-stu-id="a7afe-128">✔️ CONSIDER raising events that the end user can cancel.</span></span> <span data-ttu-id="a7afe-129">Esto solo se aplica a eventos previos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-129">This only applies to pre-events.</span></span>

 <span data-ttu-id="a7afe-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o su subclase como argumento de evento para permitir que el usuario final cancele los eventos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>

### <a name="custom-event-handler-design"></a><span data-ttu-id="a7afe-131">Diseño de controladores de eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="a7afe-131">Custom Event Handler Design</span></span>
 <span data-ttu-id="a7afe-132">Hay casos en los que `EventHandler<T>` no se puede usar, como cuando el marco de trabajo necesita trabajar con versiones anteriores de CLR, que no admiten genéricos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="a7afe-133">En tales casos, es posible que tenga que diseñar y desarrollar un delegado de controlador de eventos personalizado.</span><span class="sxs-lookup"><span data-stu-id="a7afe-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>

 <span data-ttu-id="a7afe-134">✔️ usar un tipo de valor devuelto de void para los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-134">✔️ DO use a return type of void for event handlers.</span></span>

 <span data-ttu-id="a7afe-135">Un controlador de eventos puede invocar varios métodos de control de eventos, posiblemente en varios objetos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="a7afe-136">Si los métodos de control de eventos podían devolver un valor, hubiera varios valores devueltos por cada invocación de evento.</span><span class="sxs-lookup"><span data-stu-id="a7afe-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>

 <span data-ttu-id="a7afe-137">✔️ usar `object` como el tipo del primer parámetro del controlador de eventos y llamarlo `sender` .</span><span class="sxs-lookup"><span data-stu-id="a7afe-137">✔️ DO use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>

 <span data-ttu-id="a7afe-138">✔️ usar <xref:System.EventArgs?displayProperty=nameWithType> o su subclase como el tipo del segundo parámetro del controlador de eventos y llamarlo `e` .</span><span class="sxs-lookup"><span data-stu-id="a7afe-138">✔️ DO use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>

 <span data-ttu-id="a7afe-139">❌NO tener más de dos parámetros en los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="a7afe-139">❌ DO NOT have more than two parameters on event handlers.</span></span>

 <span data-ttu-id="a7afe-140">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="a7afe-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a7afe-141">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="a7afe-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a7afe-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7afe-142">See also</span></span>

- [<span data-ttu-id="a7afe-143">Instrucciones para el diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="a7afe-143">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="a7afe-144">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="a7afe-144">Framework Design Guidelines</span></span>](index.md)
