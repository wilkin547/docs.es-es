---
description: 'Más información acerca de: Diseño de eventos'
title: Diseño de eventos
ms.date: 10/22/2008
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: d64bfb13792aa9d646560de844acddd9b7e188c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642206"
---
# <a name="event-design"></a><span data-ttu-id="9f10a-103">Diseño de eventos</span><span class="sxs-lookup"><span data-stu-id="9f10a-103">Event Design</span></span>

<span data-ttu-id="9f10a-104">Los eventos son la forma de devoluciones de llamada (construcciones que permiten al marco llamar al código de usuario) más usada.</span><span class="sxs-lookup"><span data-stu-id="9f10a-104">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="9f10a-105">Otros mecanismos de devolución de llamada son, por ejemplo, los miembros que toman delegados, los miembros virtuales y los complementos basados en interfaz. Los datos de los estudios de facilidad de uso indican que la mayoría de los desarrolladores se sienten más cómodos con los eventos que con los otros mecanismos de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9f10a-105">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="9f10a-106">Los eventos se integran perfectamente con Visual Studio y muchos lenguajes.</span><span class="sxs-lookup"><span data-stu-id="9f10a-106">Events are nicely integrated with Visual Studio and many languages.</span></span>

 <span data-ttu-id="9f10a-107">Es importante tener en cuenta que hay dos grupos de eventos: los eventos que se generan antes de que cambie una condición del sistema, denominados "eventos previos", y los eventos generados después de un cambio de condición, denominados "eventos posteriores".</span><span class="sxs-lookup"><span data-stu-id="9f10a-107">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="9f10a-108">Un ejemplo de evento previo sería `Form.Closing`, que se genera antes de que se cierre un formulario.</span><span class="sxs-lookup"><span data-stu-id="9f10a-108">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="9f10a-109">Un ejemplo de un evento posterior sería `Form.Closed`, que se produce después de cerrar un formulario.</span><span class="sxs-lookup"><span data-stu-id="9f10a-109">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>

 <span data-ttu-id="9f10a-110">✔️ Use el término "generar" para los eventos en lugar de "activar" o "desencadenar".</span><span class="sxs-lookup"><span data-stu-id="9f10a-110">✔️ DO use the term "raise" for events rather than "fire" or "trigger."</span></span>

 <span data-ttu-id="9f10a-111">✔️ Use <xref:System.EventHandler%601?displayProperty=nameWithType> en lugar de crear manualmente nuevos delegados para usarse como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-111">✔️ DO use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>

 <span data-ttu-id="9f10a-112">✔️ Recomendamos usar una subclase de <xref:System.EventArgs> como argumento de evento, a menos que esté absolutamente seguro de que el evento nunca tendrá que transportar datos al método de control de eventos, en cuyo caso puede utilizar el tipo `EventArgs` directamente.</span><span class="sxs-lookup"><span data-stu-id="9f10a-112">✔️ CONSIDER using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>

 <span data-ttu-id="9f10a-113">Si envía una API mediante `EventArgs` directamente, nunca podrá agregar datos para transportarse con el evento sin interrumpir la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="9f10a-113">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="9f10a-114">Si utiliza una subclase, incluso si inicialmente está completamente vacía, podrá agregar propiedades a la subclase cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9f10a-114">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>

 <span data-ttu-id="9f10a-115">✔️ Use un método virtual protegido para generar cada evento.</span><span class="sxs-lookup"><span data-stu-id="9f10a-115">✔️ DO use a protected virtual method to raise each event.</span></span> <span data-ttu-id="9f10a-116">Esto solo se aplica a eventos no estáticos en clases no selladas, y no en estructuras, clases selladas o eventos estáticos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-116">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>

 <span data-ttu-id="9f10a-117">El propósito del método es proporcionar una manera para que una clase derivada controle el evento mediante una invalidación.</span><span class="sxs-lookup"><span data-stu-id="9f10a-117">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="9f10a-118">La invalidación es una forma más flexible, rápida y natural de controlar eventos de clase base en clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="9f10a-118">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="9f10a-119">Por convención, el nombre del método debe empezar por "On" e ir seguido del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="9f10a-119">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>

 <span data-ttu-id="9f10a-120">La clase derivada puede decidir no llamar a la implementación base del método en su invalidación.</span><span class="sxs-lookup"><span data-stu-id="9f10a-120">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="9f10a-121">Para ello, no incluya ningún procesamiento en el método necesario para que la clase base funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="9f10a-121">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>

 <span data-ttu-id="9f10a-122">✔️ Tome un parámetro para el método protegido que genera un evento.</span><span class="sxs-lookup"><span data-stu-id="9f10a-122">✔️ DO take one parameter to the protected method that raises an event.</span></span>

 <span data-ttu-id="9f10a-123">El parámetro debe llamarse `e` y debe escribirse como la clase de argumento de evento.</span><span class="sxs-lookup"><span data-stu-id="9f10a-123">The parameter should be named `e` and should be typed as the event argument class.</span></span>

 <span data-ttu-id="9f10a-124">❌ NO pase NULL como emisor al generar un evento no estático.</span><span class="sxs-lookup"><span data-stu-id="9f10a-124">❌ DO NOT pass null as the sender when raising a nonstatic event.</span></span>

 <span data-ttu-id="9f10a-125">✔️ Pase NULL como emisor al generar un evento estático.</span><span class="sxs-lookup"><span data-stu-id="9f10a-125">✔️ DO pass null as the sender when raising a static event.</span></span>

 <span data-ttu-id="9f10a-126">❌ NO pase NULL como parámetro de datos de evento al generar un evento.</span><span class="sxs-lookup"><span data-stu-id="9f10a-126">❌ DO NOT pass null as the event data parameter when raising an event.</span></span>

 <span data-ttu-id="9f10a-127">Debe pasar `EventArgs.Empty` si no desea pasar datos al método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-127">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="9f10a-128">Los desarrolladores esperan que este parámetro no sea NULL.</span><span class="sxs-lookup"><span data-stu-id="9f10a-128">Developers expect this parameter not to be null.</span></span>

 <span data-ttu-id="9f10a-129">✔️ Recomendamos generar eventos que el usuario final pueda cancelar.</span><span class="sxs-lookup"><span data-stu-id="9f10a-129">✔️ CONSIDER raising events that the end user can cancel.</span></span> <span data-ttu-id="9f10a-130">Esto solo se aplica a los eventos previos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-130">This only applies to pre-events.</span></span>

 <span data-ttu-id="9f10a-131">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o su subclase como argumento de evento para permitir que el usuario final cancele los eventos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-131">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>

### <a name="custom-event-handler-design"></a><span data-ttu-id="9f10a-132">Diseño de controladores de eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="9f10a-132">Custom Event Handler Design</span></span>

 <span data-ttu-id="9f10a-133">Hay casos en los que no se puede usar `EventHandler<T>`, como cuando el marco necesita trabajar con versiones anteriores de CLR, que no admitía genéricos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-133">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="9f10a-134">En tales casos, es posible que tenga que diseñar y desarrollar un delegado de controlador de eventos personalizado.</span><span class="sxs-lookup"><span data-stu-id="9f10a-134">In such cases, you might need to design and develop a custom event handler delegate.</span></span>

 <span data-ttu-id="9f10a-135">✔️ Use un tipo de valor devuelto de void para los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-135">✔️ DO use a return type of void for event handlers.</span></span>

 <span data-ttu-id="9f10a-136">Un controlador de eventos puede invocar varios métodos de control de eventos, posiblemente en varios objetos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-136">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="9f10a-137">Si se permitiera que los métodos de control de eventos devolvieran un valor, habría varios valores devueltos para cada invocación de evento.</span><span class="sxs-lookup"><span data-stu-id="9f10a-137">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>

 <span data-ttu-id="9f10a-138">✔️ Use `object` como el tipo del primer parámetro del controlador de eventos y asígnele el nombre `sender`.</span><span class="sxs-lookup"><span data-stu-id="9f10a-138">✔️ DO use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>

 <span data-ttu-id="9f10a-139">✔️ Use <xref:System.EventArgs?displayProperty=nameWithType> o su subclase como el tipo del segundo parámetro del controlador de eventos y asígnele el nombre `e`.</span><span class="sxs-lookup"><span data-stu-id="9f10a-139">✔️ DO use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>

 <span data-ttu-id="9f10a-140">❌ NO tenga más de dos parámetros en los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="9f10a-140">❌ DO NOT have more than two parameters on event handlers.</span></span>

 <span data-ttu-id="9f10a-141">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="9f10a-141">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="9f10a-142">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="9f10a-142">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="9f10a-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f10a-143">See also</span></span>

- [<span data-ttu-id="9f10a-144">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="9f10a-144">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="9f10a-145">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9f10a-145">Framework Design Guidelines</span></span>](index.md)
