---
title: Nombres de miembros de tipos
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6584eecb2df652f12fd14710bb5f15933aead541
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="names-of-type-members"></a><span data-ttu-id="4b57b-102">Nombres de miembros de tipos</span><span class="sxs-lookup"><span data-stu-id="4b57b-102">Names of Type Members</span></span>
<span data-ttu-id="4b57b-103">Se realizan los tipos de miembros: métodos, propiedades, eventos, constructores y campos.</span><span class="sxs-lookup"><span data-stu-id="4b57b-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="4b57b-104">Las siguientes secciones describen las directrices para asignar nombres a los miembros de tipo.</span><span class="sxs-lookup"><span data-stu-id="4b57b-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="4b57b-105">Nombres de métodos</span><span class="sxs-lookup"><span data-stu-id="4b57b-105">Names of Methods</span></span>  
 <span data-ttu-id="4b57b-106">Porque los métodos son el medio de una acción, las instrucciones de diseño requieren que los nombres de método sea verbos o sintagmas verbales.</span><span class="sxs-lookup"><span data-stu-id="4b57b-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="4b57b-107">Sigue esta directriz también sirve para distinguir los nombres de método de propiedad y nombres de tipos, que son frases sustantivo o adjetivo.</span><span class="sxs-lookup"><span data-stu-id="4b57b-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="4b57b-108">**✓ HACER** proporcione nombres de métodos que son verbos o sintagmas verbales.</span><span class="sxs-lookup"><span data-stu-id="4b57b-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="4b57b-109">Nombres de propiedades</span><span class="sxs-lookup"><span data-stu-id="4b57b-109">Names of Properties</span></span>  
 <span data-ttu-id="4b57b-110">A diferencia de otros miembros, propiedades deberían contar con nombres adjetivo o frase.</span><span class="sxs-lookup"><span data-stu-id="4b57b-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="4b57b-111">Eso es porque una propiedad hace referencia a los datos y el nombre de la propiedad refleja.</span><span class="sxs-lookup"><span data-stu-id="4b57b-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="4b57b-112">Pascal siempre se utiliza para los nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4b57b-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="4b57b-113">**✓ HACER** nombres de las propiedades mediante un sustantivo, una frase o un adjetivo.</span><span class="sxs-lookup"><span data-stu-id="4b57b-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="4b57b-114">**X DO NOT** tienen propiedades que coinciden con el nombre de "Get" métodos como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b57b-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="4b57b-115">Este patrón normalmente indica que la propiedad debe ser realmente un método.</span><span class="sxs-lookup"><span data-stu-id="4b57b-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="4b57b-116">**✓ HACER** nombres de las propiedades de colección con una frase plural que describen los elementos de la colección en lugar de usar una frase singular seguida de "Lista" o "Colección".</span><span class="sxs-lookup"><span data-stu-id="4b57b-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="4b57b-117">**✓ HACER** nombre propiedades booleanas con una frase afirmativa (`CanSeek` en lugar de `CantSeek`).</span><span class="sxs-lookup"><span data-stu-id="4b57b-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="4b57b-118">Si lo desea, también se pueden anteponer propiedades booleanas con "Es", "puede" o "Tiene", pero sólo donde se incrementa el valor.</span><span class="sxs-lookup"><span data-stu-id="4b57b-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="4b57b-119">**Considere la posibilidad de ✓** dar a una propiedad con el mismo nombre que su tipo.</span><span class="sxs-lookup"><span data-stu-id="4b57b-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="4b57b-120">Por ejemplo, la siguiente propiedad correctamente obtiene y establece un valor de enumeración denominado `Color`, por lo que la propiedad se denomina `Color`:</span><span class="sxs-lookup"><span data-stu-id="4b57b-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="4b57b-121">Nombres de eventos</span><span class="sxs-lookup"><span data-stu-id="4b57b-121">Names of Events</span></span>  
 <span data-ttu-id="4b57b-122">Eventos siempre hacen referencia a alguna acción, ya sea uno que sea ocurra, o uno que se ha producido.</span><span class="sxs-lookup"><span data-stu-id="4b57b-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="4b57b-123">Por lo tanto, al igual que con los métodos, eventos se denominan con los verbos y tiempo de verbo se utiliza para indicar la hora cuando se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="4b57b-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="4b57b-124">**✓ HACER** nombrar los eventos con un verbo o una frase.</span><span class="sxs-lookup"><span data-stu-id="4b57b-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="4b57b-125">Algunos ejemplos son `Clicked`, `Painting`, `DroppedDown`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="4b57b-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="4b57b-126">**✓ HACER** asigne nombres de eventos con un concepto de antes y después, con los presentes y tiempos de pasado.</span><span class="sxs-lookup"><span data-stu-id="4b57b-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="4b57b-127">Por ejemplo, un evento de cierre que se produce antes de cerrar una ventana se denominaría `Closing`, y que se desencadena cuando se cierra la ventana se denominaría `Closed`.</span><span class="sxs-lookup"><span data-stu-id="4b57b-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="4b57b-128">**X DO NOT** usar "Before" o "After" prefijos o sufijos para indicar previo y eventos posteriores.</span><span class="sxs-lookup"><span data-stu-id="4b57b-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="4b57b-129">Use presente y pasado tiempos según se ha descrito.</span><span class="sxs-lookup"><span data-stu-id="4b57b-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="4b57b-130">**✓ HACER** nombre de controladores de eventos (delegados utilizados como tipos de eventos) con el sufijo "EventHandler", como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b57b-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="4b57b-131">**✓ HACER** utilizar dos parámetros con nombre `sender` y `e` en controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="4b57b-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="4b57b-132">El parámetro sender representa el objeto que provocó el evento.</span><span class="sxs-lookup"><span data-stu-id="4b57b-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="4b57b-133">El parámetro sender suele ser de tipo `object`, aunque es posible utilizar un tipo más específico.</span><span class="sxs-lookup"><span data-stu-id="4b57b-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="4b57b-134">**✓ HACER** denominar clases con el sufijo "EventArgs" de los argumentos de evento.</span><span class="sxs-lookup"><span data-stu-id="4b57b-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="4b57b-135">Nombres de campos</span><span class="sxs-lookup"><span data-stu-id="4b57b-135">Names of Fields</span></span>  
 <span data-ttu-id="4b57b-136">Se aplican las directrices de nomenclatura de campo a los campos estáticos públicos y protegidos.</span><span class="sxs-lookup"><span data-stu-id="4b57b-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="4b57b-137">Campos privados e internos no están cubiertos por instrucciones y campos de instancia público o protegido no se admiten en el [directrices de diseño de miembro](../../../docs/standard/design-guidelines/member.md).</span><span class="sxs-lookup"><span data-stu-id="4b57b-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="4b57b-138">**✓ HACER** Pascal se utiliza en nombres de campo.</span><span class="sxs-lookup"><span data-stu-id="4b57b-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="4b57b-139">**✓ HACER** nombres de los campos con un sustantivo, una frase o un adjetivo.</span><span class="sxs-lookup"><span data-stu-id="4b57b-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="4b57b-140">**X DO NOT** utiliza un prefijo para los nombres de campo.</span><span class="sxs-lookup"><span data-stu-id="4b57b-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="4b57b-141">Por ejemplo, no utilice "g_" o "s_" para indicar los campos estáticos.</span><span class="sxs-lookup"><span data-stu-id="4b57b-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="4b57b-142">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="4b57b-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4b57b-143">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4b57b-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b57b-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b57b-144">See Also</span></span>  
 [<span data-ttu-id="4b57b-145">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4b57b-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="4b57b-146">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="4b57b-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
