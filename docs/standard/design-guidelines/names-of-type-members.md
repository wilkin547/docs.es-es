---
title: Nombres de miembros de tipos
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25fe93b63c518f54ee72300f26dfcb3f3ad21d76
ms.sourcegitcommit: b6baf91310f6867223f0f32d596b451592b917b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2018
ms.locfileid: "33575354"
---
# <a name="names-of-type-members"></a><span data-ttu-id="69c72-102">Nombres de miembros de tipos</span><span class="sxs-lookup"><span data-stu-id="69c72-102">Names of Type Members</span></span>
<span data-ttu-id="69c72-103">Los tipos están conformados por miembros: métodos, propiedades, eventos, constructores y campos.</span><span class="sxs-lookup"><span data-stu-id="69c72-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="69c72-104">En las siguientes secciones se detallan las instrucciones para asignar un nombre a los miembros de tipos.</span><span class="sxs-lookup"><span data-stu-id="69c72-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="69c72-105">Nombres de métodos</span><span class="sxs-lookup"><span data-stu-id="69c72-105">Names of Methods</span></span>  
 <span data-ttu-id="69c72-106">Dado que los métodos son medios para emprender una acción, las instrucciones de diseño requieren que los nombres sean verbos o enunciados verbales.</span><span class="sxs-lookup"><span data-stu-id="69c72-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="69c72-107">Esto también permite distinguir los nombres de métodos de los de propiedades y tipos, que emplean sintagmas nominales o adjetivales.</span><span class="sxs-lookup"><span data-stu-id="69c72-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="69c72-108">**✓ DO** Los nombres de métodos deben ser verbos o enunciados verbales.</span><span class="sxs-lookup"><span data-stu-id="69c72-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="69c72-109">Nombres de propiedades</span><span class="sxs-lookup"><span data-stu-id="69c72-109">Names of Properties</span></span>  
 <span data-ttu-id="69c72-110">A diferencia de otros miembros, las propiedades deben tener nombres en forma de sintagmas nominales o adjetivales.</span><span class="sxs-lookup"><span data-stu-id="69c72-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="69c72-111">El motivo es que las propiedades hacen referencia a datos, y el nombre de estas deben reflejarlo adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="69c72-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="69c72-112">Los nombres de propiedades siempre se escriben con el formato PascalCase, es decir, las palabras se escriben unidas y se diferencian las unas de las otras por el uso de la mayúscula inicial. Este formato también es conocido como CamelCase.</span><span class="sxs-lookup"><span data-stu-id="69c72-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="69c72-113">**✓ DO** Los nombres de propiedades deben ser sustantivos, o sintagmas nominales o adjetivales.</span><span class="sxs-lookup"><span data-stu-id="69c72-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="69c72-114">**X DO NOT** Los nombres de propiedades no deben coincidir con los de otros métodos "Get", como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69c72-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="69c72-115">Este patrón suele indicar que la propiedad en realidad debería ser un método.</span><span class="sxs-lookup"><span data-stu-id="69c72-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="69c72-116">**✓ DO** Los nombres de propiedades de colecciones deben escribirse con una frase en plural que describa los elementos de una colección, en lugar de con una frase en singular seguida de los términos "lista" o "colección".</span><span class="sxs-lookup"><span data-stu-id="69c72-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="69c72-117">**✓ DO** Los nombres de propiedades booleanas deben ser un enunciado positivo, es decir, `CanSeek` en lugar de `CantSeek`.</span><span class="sxs-lookup"><span data-stu-id="69c72-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="69c72-118">De forma opcional, también puede agregar un prefijo a las propiedades booleanas, por ejemplo, "es", "puede" o "tiene", pero solo en los casos en los que realmente convenga.</span><span class="sxs-lookup"><span data-stu-id="69c72-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="69c72-119">**✓ CONSIDER** El nombre de una propiedad puede ser el mismo que el del tipo.</span><span class="sxs-lookup"><span data-stu-id="69c72-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="69c72-120">Por ejemplo, la propiedad siguiente permite obtener y establecer un valor de enumeración denominado `Color`, de modo que el nombre de la propiedad es `Color`:</span><span class="sxs-lookup"><span data-stu-id="69c72-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="69c72-121">Nombres de eventos</span><span class="sxs-lookup"><span data-stu-id="69c72-121">Names of Events</span></span>  
 <span data-ttu-id="69c72-122">Los eventos siempre hacen referencia a algún tipo de acción, ya sea una acción en curso o una ya finalizada.</span><span class="sxs-lookup"><span data-stu-id="69c72-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="69c72-123">Así pues, como en el caso de los métodos, para los nombres de los eventos se utilizan verbos, y el tiempo verbal permite indicar el momento de la acción.</span><span class="sxs-lookup"><span data-stu-id="69c72-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="69c72-124">**✓ DO** Los nombres de eventos deben ser verbos o enunciados verbales.</span><span class="sxs-lookup"><span data-stu-id="69c72-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="69c72-125">Por ejemplo, `Clicked`, `Painting`, `DroppedDown`,etc.</span><span class="sxs-lookup"><span data-stu-id="69c72-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="69c72-126">**✓ DO** Los nombres de eventos deben incluir el concepto del antes y el después mediante tiempos verbales que indiquen presente y futuro.</span><span class="sxs-lookup"><span data-stu-id="69c72-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="69c72-127">Por ejemplo, un evento de cierre que tuviera lugar antes de cerrar una ventana se llamaría `Closing`, mientras que uno que lo hiciera después se llamaría `Closed`.</span><span class="sxs-lookup"><span data-stu-id="69c72-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="69c72-128">**X DO NOT** Los nombres de eventos no deben incluir "antes" ni "después", ya sea en forma de prefijo o de sufijo, para indicar el momento del evento.</span><span class="sxs-lookup"><span data-stu-id="69c72-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="69c72-129">Utilice tiempos verbales que indiquen presente y futuro, como se ha explicado.</span><span class="sxs-lookup"><span data-stu-id="69c72-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="69c72-130">**✓ DO** Los controladores de eventos, es decir, los delegados que se usan como tipos de eventos, pueden incluir el sufijo "ControladorDeEventos", como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69c72-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="69c72-131">**✓ DO** En el caso de los controladores de eventos, use dos parámetros denominados `sender` y `e`.</span><span class="sxs-lookup"><span data-stu-id="69c72-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="69c72-132">El parámetro de envío corresponde al objeto que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="69c72-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="69c72-133">Este suele ser del tipo `object`, incluso aunque sea posible utilizar un tipo que sea más específico.</span><span class="sxs-lookup"><span data-stu-id="69c72-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="69c72-134">**✓ DO** Las clases de argumentos de eventos pueden incluir el sufijo "ArgDeEvento".</span><span class="sxs-lookup"><span data-stu-id="69c72-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="69c72-135">Nombres de campos</span><span class="sxs-lookup"><span data-stu-id="69c72-135">Names of Fields</span></span>  
 <span data-ttu-id="69c72-136">Las instrucciones relativas a la nomenclatura de los campos son aplicables a los campos estáticos públicos y protegidos.</span><span class="sxs-lookup"><span data-stu-id="69c72-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="69c72-137">En las instrucciones no se abordan los campos internos y privados. Asimismo, las [instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md) no permiten los campos de instancias públicas o protegidas.</span><span class="sxs-lookup"><span data-stu-id="69c72-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="69c72-138">**✓ DO** Los nombres de campos se escriben con el formato PascalCase, es decir, las palabras se escriben unidas y se diferencian las unas de las otras por el uso de la mayúscula inicial. Este formato también es conocido como CamelCase.</span><span class="sxs-lookup"><span data-stu-id="69c72-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="69c72-139">**✓ DO** Los nombres de campos deben ser sustantivos, o sintagmas nominales o adjetivales.</span><span class="sxs-lookup"><span data-stu-id="69c72-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="69c72-140">**X DO NOT** Los nombres de campos no deben incluir prefijos.</span><span class="sxs-lookup"><span data-stu-id="69c72-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="69c72-141">Por ejemplo, no utilice "g_" ni "s_" para indicar campos estáticos.</span><span class="sxs-lookup"><span data-stu-id="69c72-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="69c72-142">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="69c72-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="69c72-143">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="69c72-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c72-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="69c72-144">See Also</span></span>  
 [<span data-ttu-id="69c72-145">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="69c72-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="69c72-146">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="69c72-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
