---
title: Nombres de miembros de tipos
description: Obtenga información sobre las directrices para asignar nombres a los miembros de tipos en .NET como, por ejemplo, métodos, propiedades, eventos y campos.
ms.date: 10/22/2008
ms.technology: dotnet-standard
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
ms.openlocfilehash: de613673989bd174ac80adda566d04600059642d
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662503"
---
# <a name="names-of-type-members"></a><span data-ttu-id="857a2-103">Nombres de miembros de tipos</span><span class="sxs-lookup"><span data-stu-id="857a2-103">Names of Type Members</span></span>
<span data-ttu-id="857a2-104">Los tipos están conformados por miembros: métodos, propiedades, eventos, constructores y campos.</span><span class="sxs-lookup"><span data-stu-id="857a2-104">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="857a2-105">En las siguientes secciones se detallan las instrucciones para asignar un nombre a los miembros de tipos.</span><span class="sxs-lookup"><span data-stu-id="857a2-105">The following sections describe guidelines for naming type members.</span></span>

## <a name="names-of-methods"></a><span data-ttu-id="857a2-106">Nombres de métodos</span><span class="sxs-lookup"><span data-stu-id="857a2-106">Names of Methods</span></span>
 <span data-ttu-id="857a2-107">Dado que los métodos son medios para emprender una acción, las instrucciones de diseño requieren que los nombres sean verbos o enunciados verbales.</span><span class="sxs-lookup"><span data-stu-id="857a2-107">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="857a2-108">Esto también permite distinguir los nombres de métodos de los de propiedades y tipos, que emplean sintagmas nominales o adjetivales.</span><span class="sxs-lookup"><span data-stu-id="857a2-108">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>

 <span data-ttu-id="857a2-109">✔️ proporcionan nombres de métodos que son verbos o frases verbales.</span><span class="sxs-lookup"><span data-stu-id="857a2-109">✔️ DO give methods names that are verbs or verb phrases.</span></span>

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a><span data-ttu-id="857a2-110">Nombres de propiedades</span><span class="sxs-lookup"><span data-stu-id="857a2-110">Names of Properties</span></span>
 <span data-ttu-id="857a2-111">A diferencia de otros miembros, las propiedades deben tener nombres en forma de sintagmas nominales o adjetivales.</span><span class="sxs-lookup"><span data-stu-id="857a2-111">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="857a2-112">El motivo es que las propiedades hacen referencia a datos, y el nombre de estas deben reflejarlo adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="857a2-112">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="857a2-113">Los nombres de propiedades siempre se escriben con el formato PascalCase, es decir, las palabras se escriben unidas y se diferencian las unas de las otras por el uso de la mayúscula inicial. Este formato también es conocido como CamelCase.</span><span class="sxs-lookup"><span data-stu-id="857a2-113">PascalCasing is always used for property names.</span></span>

 <span data-ttu-id="857a2-114">✔️ las propiedades de nombre mediante un nombre, una frase o un adjetivo.</span><span class="sxs-lookup"><span data-stu-id="857a2-114">✔️ DO name properties using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="857a2-115">❌NO tenga propiedades que coincidan con el nombre de los métodos "Get" como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="857a2-115">❌ DO NOT have properties that match the name of "Get" methods as in the following example:</span></span>

 <span data-ttu-id="857a2-116">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span><span class="sxs-lookup"><span data-stu-id="857a2-116">`public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`</span></span>

 <span data-ttu-id="857a2-117">Este patrón suele indicar que la propiedad en realidad debería ser un método.</span><span class="sxs-lookup"><span data-stu-id="857a2-117">This pattern typically indicates that the property should really be a method.</span></span>

 <span data-ttu-id="857a2-118">✔️ las propiedades de la colección de nombres con una frase plural que describe los elementos de la colección en lugar de usar una frase singular seguida de "list" o "Collection".</span><span class="sxs-lookup"><span data-stu-id="857a2-118">✔️ DO name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection".</span></span>

 <span data-ttu-id="857a2-119">✔️ denominar propiedades booleanas con una frase afirmativa ( `CanSeek` en lugar de `CantSeek` ).</span><span class="sxs-lookup"><span data-stu-id="857a2-119">✔️ DO name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="857a2-120">Opcionalmente, también puede prefijar las propiedades booleanas con "es", "puede" o "tiene", pero solo cuando agrega valor.</span><span class="sxs-lookup"><span data-stu-id="857a2-120">Optionally, you can also prefix Boolean properties with "Is", "Can", or "Has", but only where it adds value.</span></span>

 <span data-ttu-id="857a2-121">✔️ considere la posibilidad de asignar a una propiedad el mismo nombre que su tipo.</span><span class="sxs-lookup"><span data-stu-id="857a2-121">✔️ CONSIDER giving a property the same name as its type.</span></span>

 <span data-ttu-id="857a2-122">Por ejemplo, la propiedad siguiente permite obtener y establecer un valor de enumeración denominado `Color`, de modo que el nombre de la propiedad es `Color`:</span><span class="sxs-lookup"><span data-stu-id="857a2-122">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a><span data-ttu-id="857a2-123">Nombres de eventos</span><span class="sxs-lookup"><span data-stu-id="857a2-123">Names of Events</span></span>
 <span data-ttu-id="857a2-124">Los eventos siempre hacen referencia a algún tipo de acción, ya sea una acción en curso o una ya finalizada.</span><span class="sxs-lookup"><span data-stu-id="857a2-124">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="857a2-125">Así pues, como en el caso de los métodos, para los nombres de los eventos se utilizan verbos, y el tiempo verbal permite indicar el momento de la acción.</span><span class="sxs-lookup"><span data-stu-id="857a2-125">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>

 <span data-ttu-id="857a2-126">✔️ REALIZAR eventos de nombre con un verbo o una frase verbal.</span><span class="sxs-lookup"><span data-stu-id="857a2-126">✔️ DO name events with a verb or a verb phrase.</span></span>

 <span data-ttu-id="857a2-127">Por ejemplo, `Clicked`, `Painting`, `DroppedDown`,etc.</span><span class="sxs-lookup"><span data-stu-id="857a2-127">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>

 <span data-ttu-id="857a2-128">✔️ proporcionan nombres de eventos con un concepto de antes y después, con los últimos tiempos actuales y anteriores.</span><span class="sxs-lookup"><span data-stu-id="857a2-128">✔️ DO give events names with a concept of before and after, using the present and past tenses.</span></span>

 <span data-ttu-id="857a2-129">Por ejemplo, un evento de cierre que tuviera lugar antes de cerrar una ventana se llamaría `Closing`, mientras que uno que lo hiciera después se llamaría `Closed`.</span><span class="sxs-lookup"><span data-stu-id="857a2-129">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>

 <span data-ttu-id="857a2-130">❌No use prefijos "Before" o "after" o posteriores para indicar eventos anteriores y posteriores.</span><span class="sxs-lookup"><span data-stu-id="857a2-130">❌ DO NOT use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="857a2-131">Utilice tiempos verbales que indiquen presente y futuro, como se ha explicado.</span><span class="sxs-lookup"><span data-stu-id="857a2-131">Use present and past tenses as just described.</span></span>

 <span data-ttu-id="857a2-132">✔️ los controladores de eventos de nombre (delegados usados como tipos de eventos) con el sufijo "EventHandler", como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="857a2-132">✔️ DO name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 <span data-ttu-id="857a2-133">✔️ utilizan dos parámetros denominados `sender` y `e` en los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="857a2-133">✔️ DO use two parameters named `sender` and `e` in event handlers.</span></span>

 <span data-ttu-id="857a2-134">El parámetro de envío corresponde al objeto que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="857a2-134">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="857a2-135">Este suele ser del tipo `object`, incluso aunque sea posible utilizar un tipo que sea más específico.</span><span class="sxs-lookup"><span data-stu-id="857a2-135">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>

 <span data-ttu-id="857a2-136">✔️ las clases de argumento de evento de nombre con el sufijo "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="857a2-136">✔️ DO name event argument classes with the "EventArgs" suffix.</span></span>

## <a name="names-of-fields"></a><span data-ttu-id="857a2-137">Nombres de campos</span><span class="sxs-lookup"><span data-stu-id="857a2-137">Names of Fields</span></span>
 <span data-ttu-id="857a2-138">Las instrucciones relativas a la nomenclatura de los campos son aplicables a los campos estáticos públicos y protegidos.</span><span class="sxs-lookup"><span data-stu-id="857a2-138">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="857a2-139">En las instrucciones no se abordan los campos internos y privados. Asimismo, las [instrucciones de diseño de miembros](member.md) no permiten los campos de instancias públicas o protegidas.</span><span class="sxs-lookup"><span data-stu-id="857a2-139">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](member.md).</span></span>

 <span data-ttu-id="857a2-140">✔️ usar PascalCasing en nombres de campo.</span><span class="sxs-lookup"><span data-stu-id="857a2-140">✔️ DO use PascalCasing in field names.</span></span>

 <span data-ttu-id="857a2-141">✔️ asignar nombres a los campos con un nombre, una frase o un adjetivo.</span><span class="sxs-lookup"><span data-stu-id="857a2-141">✔️ DO name fields using a noun, noun phrase, or adjective.</span></span>

 <span data-ttu-id="857a2-142">❌No use un prefijo para los nombres de campo.</span><span class="sxs-lookup"><span data-stu-id="857a2-142">❌ DO NOT use a prefix for field names.</span></span>

 <span data-ttu-id="857a2-143">Por ejemplo, no utilice "g_" ni "s_" para indicar campos estáticos.</span><span class="sxs-lookup"><span data-stu-id="857a2-143">For example, do not use "g_" or "s_" to indicate static fields.</span></span>

 <span data-ttu-id="857a2-144">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="857a2-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="857a2-145">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="857a2-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="857a2-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="857a2-146">See also</span></span>

- [<span data-ttu-id="857a2-147">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="857a2-147">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="857a2-148">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="857a2-148">Naming Guidelines</span></span>](naming-guidelines.md)
