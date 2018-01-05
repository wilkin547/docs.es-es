---
title: "Diseño de propiedades"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8f9c65dc6265daa793656177f066b97373f48ab8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="property-design"></a><span data-ttu-id="cafe6-102">Diseño de propiedades</span><span class="sxs-lookup"><span data-stu-id="cafe6-102">Property Design</span></span>
<span data-ttu-id="cafe6-103">Aunque las propiedades son técnicamente muy similares a los métodos, son bastante diferentes en cuanto a sus escenarios de uso.</span><span class="sxs-lookup"><span data-stu-id="cafe6-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="cafe6-104">Deben considerarse como campos inteligentes.</span><span class="sxs-lookup"><span data-stu-id="cafe6-104">They should be seen as smart fields.</span></span> <span data-ttu-id="cafe6-105">Y tienen la sintaxis de llamada de campos y la flexibilidad de los métodos.</span><span class="sxs-lookup"><span data-stu-id="cafe6-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="cafe6-106">**✓ HACER** crear propiedades get-only si el llamador no debe estar autorizado cambiar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cafe6-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="cafe6-107">Tenga en cuenta que, si el tipo de la propiedad es un tipo de referencia mutable, el valor de propiedad puede cambiarse incluso si la propiedad es de solo get.</span><span class="sxs-lookup"><span data-stu-id="cafe6-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="cafe6-108">**X DO NOT** proporcionan solo para establecer propiedades o propiedades con el establecedor tener accesibilidad más amplio que el captador.</span><span class="sxs-lookup"><span data-stu-id="cafe6-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="cafe6-109">Por ejemplo, no utilice las propiedades con un establecedor público y un captador protegido.</span><span class="sxs-lookup"><span data-stu-id="cafe6-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="cafe6-110">Si no se puede proporcionar el captador de propiedad, implementar la funcionalidad que un método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cafe6-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="cafe6-111">Considere la posibilidad de iniciar el nombre del método con `Set` y siga con lo que habría denominado la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cafe6-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="cafe6-112">Por ejemplo, <xref:System.AppDomain> tiene un método denominado `SetCachePath` en lugar de tener una propiedad de sólo establecimiento denominada `CachePath`.</span><span class="sxs-lookup"><span data-stu-id="cafe6-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="cafe6-113">**✓ HACER** proporcionan valores predeterminados razonables para todas las propiedades, garantizando que los valores predeterminados no producen una vulnerabilidad de seguridad o un código muy ineficaz.</span><span class="sxs-lookup"><span data-stu-id="cafe6-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="cafe6-114">**✓ HACER** permite que las propiedades que se establecerán en cualquier orden, incluso si esto da como resultado un estado temporal no válido del objeto.</span><span class="sxs-lookup"><span data-stu-id="cafe6-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="cafe6-115">Es habitual que dos o más propiedades para estar interrelacionados a un punto donde algunos valores de una propiedad pueden no ser válidos, dados los valores de otras propiedades en el mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="cafe6-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="cafe6-116">En tales casos, se deben posponer las excepciones resultantes de dicho estado no válido hasta que las propiedades interrelacionadas realmente se utilizan conjuntamente por el objeto.</span><span class="sxs-lookup"><span data-stu-id="cafe6-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="cafe6-117">**✓ HACER** conservar el valor anterior si un establecedor de propiedad inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="cafe6-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="cafe6-118">**X evitar** iniciar excepciones desde los captadores de propiedades.</span><span class="sxs-lookup"><span data-stu-id="cafe6-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="cafe6-119">Captadores de propiedades deberían ser operaciones simples y no deben tener las condiciones previas.</span><span class="sxs-lookup"><span data-stu-id="cafe6-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="cafe6-120">Si un captador puede producir una excepción, se debe probablemente volver a diseñar para que sea un método.</span><span class="sxs-lookup"><span data-stu-id="cafe6-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="cafe6-121">Tenga en cuenta que esta regla no se aplica a los indizadores, donde se espera excepciones como resultado de la validación de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="cafe6-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="cafe6-122">Diseño de propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="cafe6-122">Indexed Property Design</span></span>  
 <span data-ttu-id="cafe6-123">Una propiedad indizada es una propiedad especial que puede tener parámetros y se puede llamar con una sintaxis especial similar a la indización de matriz.</span><span class="sxs-lookup"><span data-stu-id="cafe6-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="cafe6-124">Propiedades indizadas se conocen normalmente como indizadores.</span><span class="sxs-lookup"><span data-stu-id="cafe6-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="cafe6-125">Los indizadores deben usarse solo en las API que proporcionan acceso a los elementos de una colección lógica.</span><span class="sxs-lookup"><span data-stu-id="cafe6-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="cafe6-126">Por ejemplo, una cadena es una colección de caracteres y el indizador en <xref:System.String?displayProperty=nameWithType> se agregó para tener acceso a los caracteres.</span><span class="sxs-lookup"><span data-stu-id="cafe6-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="cafe6-127">**✓ Considere la posibilidad de** utilizar indizadores para proporcionar acceso a los datos almacenados en una matriz interna.</span><span class="sxs-lookup"><span data-stu-id="cafe6-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="cafe6-128">**✓ Considere la posibilidad de** proporcionar indizadores en los tipos que representan colecciones de elementos.</span><span class="sxs-lookup"><span data-stu-id="cafe6-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="cafe6-129">**X evitar** utilizando las propiedades con más de un parámetro indizadas.</span><span class="sxs-lookup"><span data-stu-id="cafe6-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="cafe6-130">Si el diseño requiere varios parámetros, reconsidere si la propiedad representa realmente un descriptor de acceso a una colección lógica.</span><span class="sxs-lookup"><span data-stu-id="cafe6-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="cafe6-131">Si no es así, utilice métodos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cafe6-131">If it does not, use methods instead.</span></span> <span data-ttu-id="cafe6-132">Considere la posibilidad de iniciar el nombre del método con `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="cafe6-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="cafe6-133">**X evitar** indizadores con tipos de parámetro distinto de <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, o una enumeración.</span><span class="sxs-lookup"><span data-stu-id="cafe6-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="cafe6-134">Si el diseño requiere otros tipos de parámetros, fuertemente vuelva a evaluar si la API realmente representa un descriptor de acceso a una colección lógica.</span><span class="sxs-lookup"><span data-stu-id="cafe6-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="cafe6-135">Si no es así, utilice un método.</span><span class="sxs-lookup"><span data-stu-id="cafe6-135">If it does not, use a method.</span></span> <span data-ttu-id="cafe6-136">Considere la posibilidad de iniciar el nombre del método con `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="cafe6-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="cafe6-137">**✓ HACER** utilizar el nombre `Item` para propiedades indizadas a menos que haya nombre obviamente mejor (p. ej., vea el <xref:System.String.Chars%2A> propiedad `System.String`).</span><span class="sxs-lookup"><span data-stu-id="cafe6-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="cafe6-138">En C#, los indizadores son de forma predeterminada con el nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="cafe6-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="cafe6-139">La <xref:System.Runtime.CompilerServices.IndexerNameAttribute> puede usarse para personalizar este nombre.</span><span class="sxs-lookup"><span data-stu-id="cafe6-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="cafe6-140">**X DO NOT** proporciona un indizador y métodos que son semánticamente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="cafe6-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="cafe6-141">**X DO NOT** proporcionar más de una familia de indizadores sobrecargados en un tipo.</span><span class="sxs-lookup"><span data-stu-id="cafe6-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="cafe6-142">Esto se aplica por el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="cafe6-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="cafe6-143">**X DO NOT** no predeterminado de usar las propiedades indizadas.</span><span class="sxs-lookup"><span data-stu-id="cafe6-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="cafe6-144">Esto se aplica por el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="cafe6-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="cafe6-145">Eventos de notificación de cambio de propiedad</span><span class="sxs-lookup"><span data-stu-id="cafe6-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="cafe6-146">A veces resulta útil proporcionar un evento notificar al usuario de los cambios en un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cafe6-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="cafe6-147">Por ejemplo, `System.Windows.Forms.Control` genera un `TextChanged` eventos después del valor de su `Text` propiedad ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="cafe6-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="cafe6-148">**✓ Considere la posibilidad de** cuando se genera cambiar eventos de notificación cuando se modifican los valores de propiedad en las API de alto nivel (normalmente componentes de diseñador).</span><span class="sxs-lookup"><span data-stu-id="cafe6-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="cafe6-149">Si hay un caso apropiado para un usuario saber cuando cambia una propiedad de un objeto, el objeto debería generar un evento de notificación de cambio para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cafe6-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="cafe6-150">Sin embargo, es probable que tenga que vale la pena la sobrecarga para provocar estos eventos para las API de bajo nivel, como tipos base o colecciones.</span><span class="sxs-lookup"><span data-stu-id="cafe6-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="cafe6-151">Por ejemplo, <xref:System.Collections.Generic.List%601> no generaría dichos eventos cuando se agrega un nuevo elemento a la lista y `Count` cambios de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cafe6-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="cafe6-152">**✓ Considere la posibilidad de** cuando se genera los eventos de notificación cuando cambia el valor de una propiedad a través de fuerzas externas cambio.</span><span class="sxs-lookup"><span data-stu-id="cafe6-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="cafe6-153">Si cambia un valor de propiedad a través de alguna causa externa (de forma distinto mediante una llamada a métodos en el objeto), se producirá eventos indican al programador que el valor cambia y se ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="cafe6-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="cafe6-154">Un buen ejemplo es la `Text` propiedad de un control de cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="cafe6-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="cafe6-155">Cuando el usuario escribe texto en un `TextBox`, cambia automáticamente el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cafe6-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="cafe6-156">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="cafe6-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cafe6-157">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="cafe6-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafe6-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="cafe6-158">See Also</span></span>  
 [<span data-ttu-id="cafe6-159">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="cafe6-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="cafe6-160">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cafe6-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
