---
title: Diseño de eventos
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3d66d4e137c52310710f8b178167ceb3cca042c7
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="event-design"></a><span data-ttu-id="ced14-102">Diseño de eventos</span><span class="sxs-lookup"><span data-stu-id="ced14-102">Event Design</span></span>
<span data-ttu-id="ced14-103">Los eventos son la forma más utilizada de las devoluciones de llamada (construcciones que permiten el marco de trabajo llamar a código de usuario).</span><span class="sxs-lookup"><span data-stu-id="ced14-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="ced14-104">Otros mecanismos de devolución de llamada deben incluir a miembros teniendo delegados, los miembros virtuales y usar complementos basado en la interfaz. Datos de estudios de uso indican que la mayoría de los desarrolladores más cómodo mediante eventos que usen otros mecanismos de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ced14-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="ced14-105">Eventos se integran perfectamente con Visual Studio y muchos idiomas.</span><span class="sxs-lookup"><span data-stu-id="ced14-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="ced14-106">Es importante tener en cuenta que hay dos grupos de eventos: eventos generados antes de un estado de los cambios del sistema, denominados eventos anteriores y eventos que se desencadena cuando se cambia un estado, denominan eventos posteriores a la.</span><span class="sxs-lookup"><span data-stu-id="ced14-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="ced14-107">Un ejemplo de un evento previo sería `Form.Closing`, que se produce antes de que se cierra un formulario.</span><span class="sxs-lookup"><span data-stu-id="ced14-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="ced14-108">Un ejemplo de un evento posterior a la sería `Form.Closed`, que se desencadena cuando se cierra un formulario.</span><span class="sxs-lookup"><span data-stu-id="ced14-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="ced14-109">**✓ HACER** se usa el término "generar" para los eventos en lugar de "activar" o "activar".</span><span class="sxs-lookup"><span data-stu-id="ced14-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="ced14-110">**✓ HACER** use <xref:System.EventHandler%601?displayProperty=nameWithType> en lugar de crear manualmente nuevos delegados que se usará como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="ced14-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="ced14-111">**✓ Considere la posibilidad de** con una subclase de <xref:System.EventArgs> como el argumento de evento, a menos que esté totalmente seguro nunca tendrá que realizar ningún dato para el método de control de eventos el evento en cuyo caso puede utilizar la `EventArgs` escribir directamente.</span><span class="sxs-lookup"><span data-stu-id="ced14-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="ced14-112">Tanto si incluye una API mediante `EventArgs` directamente, nunca podrá agregar todos los datos se realiza con el evento sin interrumpir la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="ced14-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="ced14-113">Si usa una subclase, incluso si inicialmente completamente vacías, podrá agregar propiedades a la subclase cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ced14-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="ced14-114">**✓ HACER** utilizar un método virtual protegido para provocar cada evento.</span><span class="sxs-lookup"><span data-stu-id="ced14-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="ced14-115">Esto solo es aplicable a los eventos no estáticos en clases no selladas, no a las estructuras, clases selladas o eventos estáticos.</span><span class="sxs-lookup"><span data-stu-id="ced14-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="ced14-116">El propósito del método es proporcionar una manera para que una clase derivada para controlar el evento mediante una invalidación.</span><span class="sxs-lookup"><span data-stu-id="ced14-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="ced14-117">Reemplazar el método es una manera más flexible, más rápida y más natural para controlar los eventos de la clase base en clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="ced14-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="ced14-118">Por convención, el nombre del método debe comenzar con "On" y seguir con el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="ced14-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="ced14-119">La clase derivada puede elegir no llamar a la implementación base del método en su reemplazo.</span><span class="sxs-lookup"><span data-stu-id="ced14-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="ced14-120">Prepárese para esto, no incluya ningún procesamiento en el método que se requiere para la clase base para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="ced14-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="ced14-121">**✓ HACER** tomar un parámetro para el método protegido que genera un evento.</span><span class="sxs-lookup"><span data-stu-id="ced14-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="ced14-122">El parámetro se debe denominar `e` y debe escribirse como la clase de argumento de evento.</span><span class="sxs-lookup"><span data-stu-id="ced14-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="ced14-123">**X DO NOT** pasa null como el remitente cuando cuando se genera un evento no estático.</span><span class="sxs-lookup"><span data-stu-id="ced14-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="ced14-124">**✓ HACER** pasa null como el remitente al generar un evento estático.</span><span class="sxs-lookup"><span data-stu-id="ced14-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="ced14-125">**X DO NOT** pasa null como parámetro de datos del evento al generar un evento.</span><span class="sxs-lookup"><span data-stu-id="ced14-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="ced14-126">Debería pasar `EventArgs.Empty` si no desea pasar ningún dato para el método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="ced14-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="ced14-127">Los desarrolladores esperan este parámetro para que no sea null.</span><span class="sxs-lookup"><span data-stu-id="ced14-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="ced14-128">**Considere la posibilidad de ✓** generar eventos que se puede cancelar el usuario final.</span><span class="sxs-lookup"><span data-stu-id="ced14-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="ced14-129">Esto solo se aplica a los eventos anteriores.</span><span class="sxs-lookup"><span data-stu-id="ced14-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="ced14-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o su subclase como el argumento de evento para permitir que el usuario final pueda cancelar eventos.</span><span class="sxs-lookup"><span data-stu-id="ced14-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="ced14-131">Diseño de controlador de eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="ced14-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="ced14-132">Hay casos en los que `EventHandler<T>` no se puede usar, por ejemplo, cuando el marco de trabajo necesita trabajar con versiones anteriores de CLR, el cual no era compatible con genéricos.</span><span class="sxs-lookup"><span data-stu-id="ced14-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="ced14-133">En tales casos, deberá diseñar y desarrollar a un delegado de controlador de eventos personalizado.</span><span class="sxs-lookup"><span data-stu-id="ced14-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="ced14-134">**✓ HACER** utilizar un tipo de valor devuelto de void para controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="ced14-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="ced14-135">Un controlador de eventos puede invocar varios métodos, posiblemente en varios objetos de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="ced14-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="ced14-136">Si se permiten métodos de control de eventos para devolver un valor, habrá varios valores devueltos para cada invocación del evento.</span><span class="sxs-lookup"><span data-stu-id="ced14-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="ced14-137">**✓ HACER** usar `object` como el tipo del primer parámetro del controlador de eventos y llámelo `sender`.</span><span class="sxs-lookup"><span data-stu-id="ced14-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="ced14-138">**✓ HACER** usar <xref:System.EventArgs?displayProperty=nameWithType> o su subclase como el tipo del segundo parámetro del controlador de eventos y llámelo `e`.</span><span class="sxs-lookup"><span data-stu-id="ced14-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="ced14-139">**X DO NOT** tiene más de dos parámetros en controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="ced14-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="ced14-140">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="ced14-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ced14-141">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ced14-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced14-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="ced14-142">See Also</span></span>  
 [<span data-ttu-id="ced14-143">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="ced14-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="ced14-144">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ced14-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
