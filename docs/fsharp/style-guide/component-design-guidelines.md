---
title: 'Instrucciones de diseño del componente de F #'
description: 'Obtenga información acerca de las instrucciones para escribir componentes de F # previstos para su uso por otros llamadores.'
ms.date: 05/14/2018
ms.openlocfilehash: 7859baac76be01b2cfbdc8602b6cc417cfe5106f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="03414-103">Instrucciones de diseño del componente de F #</span><span class="sxs-lookup"><span data-stu-id="03414-103">F# component design guidelines</span></span>

<span data-ttu-id="03414-104">Este documento es un conjunto de instrucciones de diseño del componente de F # de programación, tomando como base la F # componente directrices de diseño, v14, Microsoft Research, y [otra versión](https://fsharp.org/specs/component-design-guidelines/) originalmente seleccionada y mantiene la base de Software de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="03414-105">Este documento se supone que está familiarizado con la programación en F #.</span><span class="sxs-lookup"><span data-stu-id="03414-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="03414-106">Muchas gracias a la Comunidad de F # para obtener comentarios útiles en diferentes versiones de esta guía y sus contribuciones.</span><span class="sxs-lookup"><span data-stu-id="03414-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="03414-107">Información general</span><span class="sxs-lookup"><span data-stu-id="03414-107">Overview</span></span>

<span data-ttu-id="03414-108">Este documento se examina algunos de los problemas relacionados con el diseño del componente de F # y la codificación.</span><span class="sxs-lookup"><span data-stu-id="03414-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="03414-109">Un componente puede dar lugar a cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="03414-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="03414-110">Una capa en el proyecto de F # que tiene los consumidores externos dentro de ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="03414-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="03414-111">Una biblioteca prevista para su uso en código de F # en los límites del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03414-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="03414-112">Una biblioteca prevista para su uso por cualquier lenguaje .NET Framework en los límites del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03414-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="03414-113">Una biblioteca destinada para su distribución a través de un repositorio de paquetes, como [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="03414-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="03414-114">Siguen técnicas descritas en este artículo la [cinco principios de buen código F #](index.md#five-principles-of-good-f-code)y, por tanto, usar ambos funcional y objeto de programación según corresponda.</span><span class="sxs-lookup"><span data-stu-id="03414-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="03414-115">Independientemente de la metodología, el Diseñador de componentes y la biblioteca enfrenta una serie de problemas prácticas y explicaciones al intentar crear una API que sea más fácilmente utilizable por los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="03414-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="03414-116">Una aplicación muy consciente de la [instrucciones de diseño de biblioteca de .NET](../../standard/design-guidelines/index.md) se dirigen hacia la creación de un conjunto coherente de API que forman agradables a consumir.</span><span class="sxs-lookup"><span data-stu-id="03414-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="03414-117">Instrucciones generales</span><span class="sxs-lookup"><span data-stu-id="03414-117">General guidelines</span></span>

<span data-ttu-id="03414-118">Hay algunas directrices universales que se aplican a las bibliotecas de F #, sin tener en cuenta el público previsto para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="03414-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="03414-119">Obtenga información acerca de las instrucciones de diseño de la biblioteca de .NET</span><span class="sxs-lookup"><span data-stu-id="03414-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="03414-120">Independientemente del tipo de F # codificación está realizando, es útil tener conocimientos prácticos de los [instrucciones de diseño de biblioteca de .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="03414-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="03414-121">Mayoría otros F # y los programadores de .NET se estar familiarizado con estas instrucciones y esperar que el código de .NET para que se ajuste a ellos.</span><span class="sxs-lookup"><span data-stu-id="03414-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="03414-122">Las instrucciones de diseño de la biblioteca de .NET proporcionan orientación general sobre nomenclatura, diseño de clases y interfaces, diseño de miembros (propiedades, métodos, eventos, etc.) y mucho más y son útil primer punto de referencia para una amplia variedad de instrucciones de diseño.</span><span class="sxs-lookup"><span data-stu-id="03414-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="03414-123">Agregar comentarios de documentación XML en el código</span><span class="sxs-lookup"><span data-stu-id="03414-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="03414-124">Documentación XML en las API públicas Asegúrese de que los usuarios pueden obtener gran Intellisense y Quickinfo al usar estos tipos y miembros así como documentación de creación de habilitar los archivos de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="03414-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="03414-125">Consulte la [documentación XML](../language-reference/xml-documentation.md) sobre diversas etiquetas xml que pueden usarse para marcado adicional dentro de xmldoc comentarios.</span><span class="sxs-lookup"><span data-stu-id="03414-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="03414-126">Puede usar los comentarios XML de forma abreviada (`/// comment`), o los comentarios XML estándares (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="03414-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="03414-127">Considere el uso de archivos de firma explícitas (.fsi) de biblioteca estable y las API de componentes</span><span class="sxs-lookup"><span data-stu-id="03414-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="03414-128">Uso de archivos de firmas explícita en la biblioteca de F # proporciona un resumen conciso de la API pública, que ayuda a garantizar que se conoce la superficie pública completa de la biblioteca, así como proporciona una separación clara entre documentación público e internos detalles de la implementación.</span><span class="sxs-lookup"><span data-stu-id="03414-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="03414-129">Tenga en cuenta que los archivos de firma agregan fricción ante las cambiantes de la API pública, exigiendo cambios que se realizan en los archivos de la implementación y la firma.</span><span class="sxs-lookup"><span data-stu-id="03414-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="03414-130">Como resultado, archivos de signatura deben normalmente se incorpora únicamente cuando una API se convierten en ha fortalecido y ya no se espera que cambie significativamente.</span><span class="sxs-lookup"><span data-stu-id="03414-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="03414-131">Siempre siga las prácticas recomendadas para el uso de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="03414-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="03414-132">Siga [prácticas recomendadas para el uso de cadenas en .NET](../../standard/base-types/best-practices-strings.md) instrucciones.</span><span class="sxs-lookup"><span data-stu-id="03414-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="03414-133">En concreto, indicar siempre explícitamente *intención cultural* en la conversión y la comparación de cadenas (si procede).</span><span class="sxs-lookup"><span data-stu-id="03414-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="03414-134">Directrices para F #-orientada hacia el bibliotecas</span><span class="sxs-lookup"><span data-stu-id="03414-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="03414-135">Esta sección contiene recomendaciones para el desarrollo de F # pública-orientada hacia el bibliotecas; es decir, las bibliotecas de exponer las API públicas que están destinadas a ser consumidos por los desarrolladores de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="03414-136">Hay una variedad de recomendaciones de diseño de la biblioteca aplicable específicamente para F #.</span><span class="sxs-lookup"><span data-stu-id="03414-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="03414-137">En ausencia de las recomendaciones específicas que van a continuación, las instrucciones de diseño de la biblioteca de .NET son las instrucciones de reserva.</span><span class="sxs-lookup"><span data-stu-id="03414-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="03414-138">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="03414-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="03414-139">Utilice convenciones de nomenclatura y mayúsculas y minúsculas de .NET</span><span class="sxs-lookup"><span data-stu-id="03414-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="03414-140">En la tabla siguiente sigue las convenciones de nomenclatura y uso de mayúsculas. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="03414-141">Existen pequeñas adiciones al también incluye construcciones de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="03414-142">Construcción</span><span class="sxs-lookup"><span data-stu-id="03414-142">Construct</span></span> | <span data-ttu-id="03414-143">Caso</span><span class="sxs-lookup"><span data-stu-id="03414-143">Case</span></span> | <span data-ttu-id="03414-144">Parte</span><span class="sxs-lookup"><span data-stu-id="03414-144">Part</span></span> | <span data-ttu-id="03414-145">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="03414-145">Examples</span></span> | <span data-ttu-id="03414-146">Notas</span><span class="sxs-lookup"><span data-stu-id="03414-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="03414-147">Tipos concretos</span><span class="sxs-lookup"><span data-stu-id="03414-147">Concrete types</span></span> | <span data-ttu-id="03414-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-148">PascalCase</span></span> | <span data-ttu-id="03414-149">Sustantivo o adjetivo</span><span class="sxs-lookup"><span data-stu-id="03414-149">Noun/ adjective</span></span> | <span data-ttu-id="03414-150">Lista, doble, complejo</span><span class="sxs-lookup"><span data-stu-id="03414-150">List, Double, Complex</span></span> | <span data-ttu-id="03414-151">Tipos concretos son estructuras, clases, enumeraciones, delegados, registros y uniones.</span><span class="sxs-lookup"><span data-stu-id="03414-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="03414-152">Aunque los nombres de tipo son tradicionalmente en minúsculas en OCaml, F # ha adoptado el esquema de nomenclatura de .NET para los tipos.</span><span class="sxs-lookup"><span data-stu-id="03414-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="03414-153">DLL</span><span class="sxs-lookup"><span data-stu-id="03414-153">DLLs</span></span>           | <span data-ttu-id="03414-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-154">PascalCase</span></span> |                 | <span data-ttu-id="03414-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="03414-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="03414-156">Etiquetas de unión</span><span class="sxs-lookup"><span data-stu-id="03414-156">Union tags</span></span>     | <span data-ttu-id="03414-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-157">PascalCase</span></span> | <span data-ttu-id="03414-158">nombre</span><span class="sxs-lookup"><span data-stu-id="03414-158">Noun</span></span> | <span data-ttu-id="03414-159">Algunos, agregar, correcto</span><span class="sxs-lookup"><span data-stu-id="03414-159">Some, Add, Success</span></span> | <span data-ttu-id="03414-160">No utilice un prefijo en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="03414-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="03414-161">Utilizar opcionalmente un prefijo cuando interno, como ''' Escriba los equipos = TAlpha</span><span class="sxs-lookup"><span data-stu-id="03414-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="03414-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="03414-162">TBeta</span></span> | <span data-ttu-id="03414-163">TDelta.'' '</span><span class="sxs-lookup"><span data-stu-id="03414-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="03414-164">evento</span><span class="sxs-lookup"><span data-stu-id="03414-164">Event</span></span>          | <span data-ttu-id="03414-165">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-165">PascalCase</span></span> | <span data-ttu-id="03414-166">Verbo</span><span class="sxs-lookup"><span data-stu-id="03414-166">Verb</span></span> | <span data-ttu-id="03414-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="03414-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="03414-168">Excepciones</span><span class="sxs-lookup"><span data-stu-id="03414-168">Exceptions</span></span>     | <span data-ttu-id="03414-169">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-169">PascalCase</span></span> |      | <span data-ttu-id="03414-170">WebException</span><span class="sxs-lookup"><span data-stu-id="03414-170">WebException</span></span> | <span data-ttu-id="03414-171">Nombre debe terminar con "Exception".</span><span class="sxs-lookup"><span data-stu-id="03414-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="03414-172">Campo</span><span class="sxs-lookup"><span data-stu-id="03414-172">Field</span></span>          | <span data-ttu-id="03414-173">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-173">PascalCase</span></span> | <span data-ttu-id="03414-174">nombre</span><span class="sxs-lookup"><span data-stu-id="03414-174">Noun</span></span> | <span data-ttu-id="03414-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="03414-175">CurrentName</span></span>  | |
| <span data-ttu-id="03414-176">Tipos de interfaz</span><span class="sxs-lookup"><span data-stu-id="03414-176">Interface types</span></span> |  <span data-ttu-id="03414-177">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-177">PascalCase</span></span> | <span data-ttu-id="03414-178">Sustantivo o adjetivo</span><span class="sxs-lookup"><span data-stu-id="03414-178">Noun/ adjective</span></span> | <span data-ttu-id="03414-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="03414-179">IDisposable</span></span> | <span data-ttu-id="03414-180">Nombre debe comenzar con "I".</span><span class="sxs-lookup"><span data-stu-id="03414-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="03414-181">Método</span><span class="sxs-lookup"><span data-stu-id="03414-181">Method</span></span> |  <span data-ttu-id="03414-182">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-182">PascalCase</span></span> |  <span data-ttu-id="03414-183">Verbo</span><span class="sxs-lookup"><span data-stu-id="03414-183">Verb</span></span> | <span data-ttu-id="03414-184">ToString</span><span class="sxs-lookup"><span data-stu-id="03414-184">ToString</span></span> | |
| <span data-ttu-id="03414-185">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="03414-185">Namespace</span></span> | <span data-ttu-id="03414-186">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-186">PascalCase</span></span> | | <span data-ttu-id="03414-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="03414-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="03414-188">Generalmente se utiliza `<Organization>.<Technology>[.<Subnamespace>]`, drop aunque la organización si la tecnología es independiente de la organización.</span><span class="sxs-lookup"><span data-stu-id="03414-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="03414-189">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03414-189">Parameters</span></span> | <span data-ttu-id="03414-190">camelCase</span><span class="sxs-lookup"><span data-stu-id="03414-190">camelCase</span></span> | <span data-ttu-id="03414-191">nombre</span><span class="sxs-lookup"><span data-stu-id="03414-191">Noun</span></span> |  <span data-ttu-id="03414-192">typeName, transformar, de intervalo</span><span class="sxs-lookup"><span data-stu-id="03414-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="03414-193">permitir que los valores (internos)</span><span class="sxs-lookup"><span data-stu-id="03414-193">let values (internal)</span></span> | <span data-ttu-id="03414-194">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-194">camelCase or PascalCase</span></span> | <span data-ttu-id="03414-195">Nombre / verbo</span><span class="sxs-lookup"><span data-stu-id="03414-195">Noun/ verb</span></span> |  <span data-ttu-id="03414-196">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="03414-196">getValue, myTable</span></span> |
| <span data-ttu-id="03414-197">permitir que los valores (externo)</span><span class="sxs-lookup"><span data-stu-id="03414-197">let values (external)</span></span> | <span data-ttu-id="03414-198">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-198">camelCase or PascalCase</span></span> | <span data-ttu-id="03414-199">Nombre/verbo</span><span class="sxs-lookup"><span data-stu-id="03414-199">Noun/verb</span></span>  | <span data-ttu-id="03414-200">List.Map, Dates.Today</span><span class="sxs-lookup"><span data-stu-id="03414-200">List.map, Dates.Today</span></span> | <span data-ttu-id="03414-201">valores de límite permiten a menudo son públicos al seguir los patrones de diseño funcional tradicional.</span><span class="sxs-lookup"><span data-stu-id="03414-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="03414-202">Sin embargo, generalmente se utiliza PascalCase cuando el identificador se puede usar en otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="03414-203">Property</span><span class="sxs-lookup"><span data-stu-id="03414-203">Property</span></span>  | <span data-ttu-id="03414-204">PascalCase</span><span class="sxs-lookup"><span data-stu-id="03414-204">PascalCase</span></span>  | <span data-ttu-id="03414-205">Sustantivo o adjetivo</span><span class="sxs-lookup"><span data-stu-id="03414-205">Noun/ adjective</span></span>  | <span data-ttu-id="03414-206">IsEndOfFile, color de fondo</span><span class="sxs-lookup"><span data-stu-id="03414-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="03414-207">Propiedades booleanas por lo general uso y puede y debe ser afirmativa, como en IsEndOfFile, no IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="03414-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="03414-208">Evite las abreviaturas</span><span class="sxs-lookup"><span data-stu-id="03414-208">Avoid abbreviations</span></span>

<span data-ttu-id="03414-209">Las instrucciones de .NET desaconseja el uso de las abreviaturas (por ejemplo, "usar `OnButtonClick` en lugar de `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="03414-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="03414-210">Abreviaturas comunes, como `Async` para "Asincrónico", que se tolera.</span><span class="sxs-lookup"><span data-stu-id="03414-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="03414-211">A veces se pasa por alto esta directriz para la programación funcional; Por ejemplo, `List.iter` usa una abreviatura de "repetir".</span><span class="sxs-lookup"><span data-stu-id="03414-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="03414-212">Por este motivo, con abreviaturas tiende a tolerar un mayor grado de F #-a-programación en F #, pero se deben evitar en general todavía en el diseño de los componentes públicos.</span><span class="sxs-lookup"><span data-stu-id="03414-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="03414-213">Evitar conflictos de nombres las mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="03414-213">Avoid casing name collisions</span></span>

<span data-ttu-id="03414-214">Las instrucciones de .NET decir que las mayúsculas y minúsculas por sí solo no se puede usar para eliminar la ambigüedad de conflictos de nombres, ya que algunos lenguajes de cliente (por ejemplo, Visual Basic) distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="03414-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="03414-215">Utilice acrónimos cuando resulte apropiado</span><span class="sxs-lookup"><span data-stu-id="03414-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="03414-216">Acrónimos como XML no son las abreviaturas y se usan ampliamente en las bibliotecas de .NET en forma sin mayúsculas (Xml).</span><span class="sxs-lookup"><span data-stu-id="03414-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="03414-217">Solo deben utilizarse acrónimos conocidos, ampliamente reconocidos.</span><span class="sxs-lookup"><span data-stu-id="03414-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="03414-218">Utilice PascalCase para los nombres de parámetro genérico</span><span class="sxs-lookup"><span data-stu-id="03414-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="03414-219">Utilice PascalCase para nombres de parámetro genérico en las API públicas, incluidos los de F #-orientada hacia las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="03414-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="03414-220">En concreto, use nombres como `T`, `U`, `T1`, `T2` para los parámetros genéricos arbitrarios y nombres específicos tienen sentido, a continuación, en F #-orientados al público bibliotecas usen nombres como `Key`, `Value`, `Arg`(pero no por ejemplo, `TKey`).</span><span class="sxs-lookup"><span data-stu-id="03414-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="03414-221">Utilizar PascalCase o camelCase para funciones públicas y valores en los módulos de F #</span><span class="sxs-lookup"><span data-stu-id="03414-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="03414-222">camelCase se utiliza para funciones públicas que están diseñadas para utilizarse sin calificar (por ejemplo, `invalidArg`) y para las funciones de colección estándar de"" (por ejemplo, List.map).</span><span class="sxs-lookup"><span data-stu-id="03414-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="03414-223">En ambos de estos casos, los nombres de función actúan como palabras clave en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="03414-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="03414-224">Diseño de objeto, el tipo y el módulo</span><span class="sxs-lookup"><span data-stu-id="03414-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="03414-225">Usar espacios de nombres o módulos para contener los tipos y módulos</span><span class="sxs-lookup"><span data-stu-id="03414-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="03414-226">Cada archivo de F # en un componente debe comenzar con una declaración de espacio de nombres o una declaración de módulo.</span><span class="sxs-lookup"><span data-stu-id="03414-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="03414-227">o</span><span class="sxs-lookup"><span data-stu-id="03414-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="03414-228">Las diferencias entre el uso de módulos y espacios de nombres para organizar el código en el nivel superior son como sigue:</span><span class="sxs-lookup"><span data-stu-id="03414-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="03414-229">Espacios de nombres pueden abarcar varios archivos</span><span class="sxs-lookup"><span data-stu-id="03414-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="03414-230">Espacios de nombres no pueden contener funciones de F # a menos que estén dentro de un módulo interno</span><span class="sxs-lookup"><span data-stu-id="03414-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="03414-231">El código de cualquier módulo determinado debe estar dentro de un único archivo</span><span class="sxs-lookup"><span data-stu-id="03414-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="03414-232">Módulos de nivel superior pueden contener funciones de F # sin necesidad de un módulo interno</span><span class="sxs-lookup"><span data-stu-id="03414-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="03414-233">La elección entre un módulo o espacio de nombres de nivel superior afecta a la forma compilada del código y, por tanto, afectará a la vista de otros lenguajes .NET su API finalmente se debe consumir fuera del código de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="03414-234">Usar métodos y propiedades para las operaciones intrínsecas a tipos de objeto</span><span class="sxs-lookup"><span data-stu-id="03414-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="03414-235">Cuando se trabaja con objetos, es mejor para asegurarse de que se implementa funcionalidad consumible como métodos y propiedades de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="03414-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="03414-236">La mayor parte de la funcionalidad para un miembro determinado necesita no necesariamente se implementan en ese miembro, pero debe ser la pieza consumible de esa funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="03414-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="03414-237">Usar las clases para encapsular el estado mutable</span><span class="sxs-lookup"><span data-stu-id="03414-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="03414-238">En F #, esto solo debe hacerse donde que estado no está ya encapsulado por otra construcción del lenguaje, como un cierre, la expresión de secuencia o el cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="03414-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="03414-239">Usar interfaces para agrupar las operaciones relacionadas con</span><span class="sxs-lookup"><span data-stu-id="03414-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="03414-240">Usar tipos de interfaz para representar un conjunto de operaciones.</span><span class="sxs-lookup"><span data-stu-id="03414-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="03414-241">Esto es preferible a otras opciones, como las tuplas de funciones o registros de funciones.</span><span class="sxs-lookup"><span data-stu-id="03414-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="03414-242">Prioridad para:</span><span class="sxs-lookup"><span data-stu-id="03414-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="03414-243">Las interfaces son conceptos de primera clase en. NET, que puede usar para lograr qué funciones normalmente le proporcionaría.</span><span class="sxs-lookup"><span data-stu-id="03414-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="03414-244">Además, puede utilizarse para codificar tipos existenciales en el programa, que no puedan registros de funciones.</span><span class="sxs-lookup"><span data-stu-id="03414-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="03414-245">Usar un módulo a las funciones de grupo que actúan en colecciones</span><span class="sxs-lookup"><span data-stu-id="03414-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="03414-246">Cuando se define un tipo de colección, considere la posibilidad de proporcionar un conjunto estándar de operaciones, como `CollectionType.map` y `CollectionType.iter`) para los nuevos tipos de colección.</span><span class="sxs-lookup"><span data-stu-id="03414-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="03414-247">Si incluye un módulo de este tipo, siga las convenciones de nomenclatura estándares para las funciones que se encuentra en FSharp.Core.</span><span class="sxs-lookup"><span data-stu-id="03414-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="03414-248">Usar un módulo a las funciones de grupo para funciones comunes canónicas, especialmente en matemáticas y bibliotecas DSL</span><span class="sxs-lookup"><span data-stu-id="03414-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="03414-249">Por ejemplo, `Microsoft.FSharp.Core.Operators` es una colección automáticamente abierta de funciones de nivel superior (como `abs` y `sin`) proporcionada por FSharp.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="03414-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="03414-250">Igualmente, una biblioteca de las estadísticas podría incluir un módulo con funciones `erf` y `erfc`, donde este módulo está diseñado para que se abran explícitamente o automáticamente.</span><span class="sxs-lookup"><span data-stu-id="03414-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="03414-251">Considere el uso de RequireQualifiedAccess y cuidadosamente aplicar atributos AutoOpen</span><span class="sxs-lookup"><span data-stu-id="03414-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="03414-252">Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que no se puede abrir el módulo y que las referencias a los elementos del módulo requieren explícita calificar el acceso.</span><span class="sxs-lookup"><span data-stu-id="03414-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="03414-253">Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.</span><span class="sxs-lookup"><span data-stu-id="03414-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="03414-254">Esto es útil cuando las funciones y los valores en el módulo tienen nombres que es probables que entran en conflicto con los nombres de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="03414-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="03414-255">Que necesiten acceso completo puede aumentar considerablemente el mantenimiento a largo plazo y evolvability de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="03414-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="03414-256">Agregar el `[<AutoOpen>]` atributo a un módulo significa que el módulo se abrirá cuando se abre el espacio de nombres contenedor.</span><span class="sxs-lookup"><span data-stu-id="03414-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="03414-257">El `[<AutoOpen>]` también se puede aplicar el atributo a un ensamblado para indicar un módulo que se abrirá automáticamente cuando se hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03414-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="03414-258">Por ejemplo, una biblioteca de estadísticas **MathsHeaven.Statistics** podría contener una `module MathsHeaven.Statistics.Operators` que contienen funciones `erf` y `erfc`.</span><span class="sxs-lookup"><span data-stu-id="03414-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="03414-259">Es razonable marcar este módulo como `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="03414-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="03414-260">Esto significa `open MathsHeaven.Statistics` también abrirá este módulo y poner los nombres `erf` y `erfc` en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="03414-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="03414-261">Otra buena el uso de `[<AutoOpen>]` es para módulos que contienen métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="03414-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="03414-262">Un uso excesivo de `[<AutoOpen>]` hace que las contaminado espacios de nombres y el atributo debe utilizarse con cuidado.</span><span class="sxs-lookup"><span data-stu-id="03414-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="03414-263">Para determinadas bibliotecas en dominios específicos, un uso razonable de `[<AutoOpen>]` puede dar lugar a una mejor utilización.</span><span class="sxs-lookup"><span data-stu-id="03414-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="03414-264">Considere la posibilidad de definir miembros de operador en las clases donde es adecuado usar operadores conocidos</span><span class="sxs-lookup"><span data-stu-id="03414-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="03414-265">A veces las clases se usan para crear estructuras matemáticas como vectores.</span><span class="sxs-lookup"><span data-stu-id="03414-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="03414-266">Cuando el dominio que se está modelando tiene operadores conocidos, definiéndolos como miembros intrínsecos de la clase es útil.</span><span class="sxs-lookup"><span data-stu-id="03414-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="03414-267">Esta guía se corresponde con las instrucciones generales de .NET para estos tipos.</span><span class="sxs-lookup"><span data-stu-id="03414-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="03414-268">Sin embargo, puede ser importante además en F # codificaciones, ya que esto permite que estos tipos para usarse en métodos con restricciones de miembro, como List.sumBy y junto con funciones de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="03414-269">Considere la posibilidad de usar CompiledName para proporcionar una. Nombre descriptivo de la red para otros consumidores de lenguaje de .NET</span><span class="sxs-lookup"><span data-stu-id="03414-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="03414-270">En ocasiones, puede que desee algo en un estilo de nombre para los consumidores de F # (por ejemplo, un miembro estático en minúscula para que aparezca como si fuera una función de módulo enlazada), pero tienen un estilo diferente para el nombre cuando se compila en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03414-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="03414-271">Puede usar el `[<CompiledName>]` atributo para proporcionar un estilo diferente para consumir el ensamblado de código no F #.</span><span class="sxs-lookup"><span data-stu-id="03414-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="03414-272">Mediante el uso de `[<CompiledName>]`, puede utilizar las convenciones de nomenclatura .NET para F # no los consumidores del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03414-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="03414-273">Utilizar una sobrecarga de método para las funciones de miembro, si al hacerlo consigue una API más sencilla</span><span class="sxs-lookup"><span data-stu-id="03414-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="03414-274">Sobrecarga de métodos es una herramienta eficaz para simplificar una API que quizás deba realizar una funcionalidad similar, pero con argumentos u opciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="03414-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="03414-275">En F #, es más habitual de sobrecarga en el número de argumentos en lugar de tipos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="03414-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="03414-276">Ocultar las representaciones de registro y tipos de unión si el diseño de estos tipos tiene susceptibles de evolucionar</span><span class="sxs-lookup"><span data-stu-id="03414-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="03414-277">Evitar revelar representaciones concretas de objetos.</span><span class="sxs-lookup"><span data-stu-id="03414-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="03414-278">Por ejemplo, la representación concreta de <xref:System.DateTime> por la API externa, pública del diseño de biblioteca de .NET no se revelen los valores.</span><span class="sxs-lookup"><span data-stu-id="03414-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="03414-279">En tiempo de ejecución, Common Language Runtime sabe la implementación confirma que se utilizará a lo largo de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="03414-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="03414-280">Sin embargo, código compilado no propio recoge las dependencias de la representación en forma concreta.</span><span class="sxs-lookup"><span data-stu-id="03414-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="03414-281">Evite el uso de la herencia de implementación para la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="03414-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="03414-282">En F #, apenas se usa la herencia de implementación.</span><span class="sxs-lookup"><span data-stu-id="03414-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="03414-283">Además, las jerarquías de herencia son a menudo complejo y difícil de modificar cuando llegan los nuevos requisitos.</span><span class="sxs-lookup"><span data-stu-id="03414-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="03414-284">Implementación de la herencia sigue existiendo en F # para la compatibilidad y raros casos donde es la mejor solución para un problema, pero técnicas alternativas deben obtenerse en los programas de F # cuando se diseña para polimorfismo, como la implementación de interfaz.</span><span class="sxs-lookup"><span data-stu-id="03414-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="03414-285">Firmas de función y miembro</span><span class="sxs-lookup"><span data-stu-id="03414-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="03414-286">Tuplas de uso para los valores devueltos cuando se devuelve un número reducido de varios valores no relacionados</span><span class="sxs-lookup"><span data-stu-id="03414-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="03414-287">Este es un buen ejemplo del uso de una tupla en un tipo de valor devuelto:</span><span class="sxs-lookup"><span data-stu-id="03414-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="03414-288">Para devolver los tipos que contiene muchos componentes o, si los componentes están relacionadas con una sola entidad de identificación, considere la posibilidad de usar un tipo con nombre en lugar de una tupla.</span><span class="sxs-lookup"><span data-stu-id="03414-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="03414-289">Use `Async<T>` para programación asincrónica en los límites de API de F #</span><span class="sxs-lookup"><span data-stu-id="03414-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="03414-290">Si hay una operación sincrónica correspondiente denominada `Operation` que devuelve un `T`, a continuación, la operación asincrónica debe denominarse `AsyncOperation` si devuelve `Async<T>` o `OperationAsync` si devuelve `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="03414-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="03414-291">Los tipos utilizados frecuentemente de .NET que exponen métodos Begin/End, considere la posibilidad de usar `Async.FromBeginEnd` para escribir métodos de extensión como una fachada para proporcionar el F # async modelo de programación a las API de .NET.</span><span class="sxs-lookup"><span data-stu-id="03414-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="03414-292">Excepciones</span><span class="sxs-lookup"><span data-stu-id="03414-292">Exceptions</span></span>

<span data-ttu-id="03414-293">Las excepciones son excepcionales en. NET; es decir, no deben ocurrir con frecuencia en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="03414-293">Exceptions are exceptional in .NET; that is, they should not occur frequently at runtime.</span></span> <span data-ttu-id="03414-294">Cuando lo hacen, es útil la información que contienen.</span><span class="sxs-lookup"><span data-stu-id="03414-294">When they do, the information they contain is valuable.</span></span> <span data-ttu-id="03414-295">Las excepciones son un núcleo de primera clase concepto de. NET; TI, por lo que se indica a continuación que corresponda de la aplicación de las excepciones que debe usarse como parte del diseño de la interfaz de un componente.</span><span class="sxs-lookup"><span data-stu-id="03414-295">Exceptions are a core first class concept of .NET; it hence follows that appropriate application of the Exceptions should be used as part of the design of the interface of a component.</span></span>

#### <a name="follow-the-net-guidelines-for-exceptions"></a><span data-ttu-id="03414-296">Siga las instrucciones de .NET para las excepciones</span><span class="sxs-lookup"><span data-stu-id="03414-296">Follow the .NET guidelines for exceptions</span></span>

<span data-ttu-id="03414-297">El [instrucciones de diseño de biblioteca de .NET](../../standard/design-guidelines/exceptions.md) ofrece excelente consejos sobre el uso de las excepciones producidas en el contexto de toda la programación. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-297">The [.NET Library Design Guidelines](../../standard/design-guidelines/exceptions.md) give excellent advice on the use of exceptions in the context of all .NET programming.</span></span> <span data-ttu-id="03414-298">Algunas de estas instrucciones son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="03414-298">Some of these guidelines are as follows:</span></span>

* <span data-ttu-id="03414-299">No uses excepciones para el flujo de control normal.</span><span class="sxs-lookup"><span data-stu-id="03414-299">Do not use exceptions for normal flow of control.</span></span> <span data-ttu-id="03414-300">Aunque esta técnica suele utilizarse en lenguajes como OCaml, es propensa a errores y puede ser ineficaz en. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-300">Although this technique is often used in languages such as OCaml, it is bug-prone and can be inefficient on .NET.</span></span> <span data-ttu-id="03414-301">En su lugar, considere la posibilidad de devolver un `None` valor para indicar un error que es común o se espera algo de la opción.</span><span class="sxs-lookup"><span data-stu-id="03414-301">Instead, consider returning a `None` option value to indicate a failure that is a common or expected occurrence.</span></span>

* <span data-ttu-id="03414-302">Documente las excepciones producidas por los componentes cuando se utiliza una función de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="03414-302">Document exceptions thrown by your components when a function is used incorrectly.</span></span>

* <span data-ttu-id="03414-303">Siempre que sea posible, emplear excepciones existentes de los espacios de nombres del sistema.</span><span class="sxs-lookup"><span data-stu-id="03414-303">Where possible, employ existing exceptions from the System namespaces.</span></span> <span data-ttu-id="03414-304">Evitar <xref:System.ApplicationException>, aunque.</span><span class="sxs-lookup"><span data-stu-id="03414-304">Avoid <xref:System.ApplicationException>, though.</span></span>

* <span data-ttu-id="03414-305">No genere <xref:System.Exception> cuando escaparán al código de usuario.</span><span class="sxs-lookup"><span data-stu-id="03414-305">Do not throw <xref:System.Exception> when it will escape to user code.</span></span> <span data-ttu-id="03414-306">Esto incluye evitar el uso de `failwith`, `failwithf`, que son funciones útiles para su uso en secuencias de comandos y código en desarrollo, pero se deben quitar del código de biblioteca de F # en favor de producir un tipo de excepción más específico.</span><span class="sxs-lookup"><span data-stu-id="03414-306">This includes avoiding the use of `failwith`, `failwithf`, which are handy functions for use in scripting and for code under development, but should be removed from F# library code in favor of throwing a more specific exception type.</span></span>

* <span data-ttu-id="03414-307">Use `nullArg`, `invalidArg`, y `invalidOp` como mecanismo para producir <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, y <xref:System.InvalidOperationException> cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="03414-307">Use `nullArg`, `invalidArg`, and `invalidOp` as the mechanism to throw <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, and <xref:System.InvalidOperationException> when appropriate.</span></span>

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a><span data-ttu-id="03414-308">Considere el uso de valores de las opciones para los tipos de valor devueltos cuando no hay una situación excepcional</span><span class="sxs-lookup"><span data-stu-id="03414-308">Consider using option values for return types when failure is not an exceptional scenario</span></span>

<span data-ttu-id="03414-309">El método de .NET a las excepciones es que debe ser "excepcionales;" es decir, que ocurran relativamente con poca frecuencia.</span><span class="sxs-lookup"><span data-stu-id="03414-309">The .NET approach to exceptions is that they should be “exceptional”; that is, they should occur relatively infrequently.</span></span> <span data-ttu-id="03414-310">Sin embargo, algunas operaciones (por ejemplo, la búsqueda de una tabla) pueden producir errores con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="03414-310">However, some operations (for example, searching a table) may fail frequently.</span></span> <span data-ttu-id="03414-311">Los valores de opción de F # son una excelente forma para representar los tipos devueltos de estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="03414-311">F# option values are an excellent way to represent the return types of these operations.</span></span> <span data-ttu-id="03414-312">Estas operaciones convencionalmente empiezan con el prefijo de nombre "try":</span><span class="sxs-lookup"><span data-stu-id="03414-312">These operations conventionally start with the name prefix “try”:</span></span>

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a><span data-ttu-id="03414-313">Miembros de extensión</span><span class="sxs-lookup"><span data-stu-id="03414-313">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="03414-314">Aplicar cuidadosamente los miembros de extensión de F # en F #-a-F # componentes</span><span class="sxs-lookup"><span data-stu-id="03414-314">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="03414-315">Miembros de extensión de F # normalmente deben usarse solo para las operaciones que se encuentran en el cierre de operaciones intrínsecos asociado a un tipo en la mayoría de los modos de uso.</span><span class="sxs-lookup"><span data-stu-id="03414-315">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="03414-316">Un uso habitual consiste en proporcionan API que son más idiomáticas a F # para varios tipos. NET:</span><span class="sxs-lookup"><span data-stu-id="03414-316">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="03414-317">Tipos de unión</span><span class="sxs-lookup"><span data-stu-id="03414-317">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="03414-318">Usar uniones discriminadas en lugar de jerarquías de clases para los datos de estructura de árbol</span><span class="sxs-lookup"><span data-stu-id="03414-318">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="03414-319">Las estructuras de árbol son definidos de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="03414-319">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="03414-320">Esto es difícil con herencia, pero elegante con uniones discriminadas.</span><span class="sxs-lookup"><span data-stu-id="03414-320">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="03414-321">Que representa los datos en forma de árbol con uniones discriminadas también permite beneficiarse de exhaustiveness de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="03414-321">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="03414-322">Use `[<RequireQualifiedAccess>]` en tipos de unión cuyos nombres casos no son lo suficientemente exclusivos</span><span class="sxs-lookup"><span data-stu-id="03414-322">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="03414-323">Es probable que se encuentre en un dominio donde el mismo nombre es el nombre más adecuado para realizar diferentes tareas, como casos de unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="03414-323">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="03414-324">Puede usar `[<RequireQualifiedAccess>]` para eliminar la ambigüedad de los nombres de casos con el fin de evitar que se produzca errores confusos debido al sombreado depende de la ordenación de `open` instrucciones</span><span class="sxs-lookup"><span data-stu-id="03414-324">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="03414-325">Ocultar las representaciones de las uniones discriminadas para las API compatibles binarias si el diseño de estos tipos tiene susceptibles de evolucionar</span><span class="sxs-lookup"><span data-stu-id="03414-325">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="03414-326">Tipos de uniones se basan en F # coincidencia formularios para un modelo de programación conciso.</span><span class="sxs-lookup"><span data-stu-id="03414-326">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="03414-327">Como se mencionó anteriormente, debe evitar revelar representaciones de datos concretos si es probable que evolucione el diseño de estos tipos.</span><span class="sxs-lookup"><span data-stu-id="03414-327">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="03414-328">Por ejemplo, se puede ocultar la representación de una unión discriminada con una declaración privada o interna, o mediante un archivo de signatura.</span><span class="sxs-lookup"><span data-stu-id="03414-328">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="03414-329">Si revelan uniones discriminadas forma indiscriminada, quizá le resulte difícil versión la biblioteca sin interrumpir el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="03414-329">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="03414-330">En su lugar, considere la posibilidad de que revelen uno o varios modelos activos para permitir la coincidencia sobre los valores de los tipos de patrones.</span><span class="sxs-lookup"><span data-stu-id="03414-330">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="03414-331">Modelos activos proporcionan un mecanismo alternativo para proporcionar a los consumidores de F # con el patrón de búsqueda de coincidencias al evitar exponer directamente los tipos de unión de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-331">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="03414-332">Las funciones insertadas y las restricciones de miembro</span><span class="sxs-lookup"><span data-stu-id="03414-332">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="03414-333">Definir los algoritmos numéricos genéricos mediante funciones inline con restricciones de miembro implícito y tipos genéricos resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="03414-333">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="03414-334">Las restricciones de miembro aritméticos y las restricciones de comparación de F # son un estándar para la programación de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-334">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="03414-335">Por ejemplo, considere el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="03414-335">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="03414-336">El tipo de esta función es como sigue:</span><span class="sxs-lookup"><span data-stu-id="03414-336">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="03414-337">Se trata de una función adecuada para una API pública en una biblioteca de matemática.</span><span class="sxs-lookup"><span data-stu-id="03414-337">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="03414-338">Evite el uso de restricciones de miembro para simular las clases de tipos y duck escribiendo</span><span class="sxs-lookup"><span data-stu-id="03414-338">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="03414-339">Es posible simular "agacha escribiendo" mediante las restricciones de miembro de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-339">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="03414-340">Sin embargo, los miembros que hacen que utilizar esta propiedad no está en general se utiliza en F #-a-diseños de biblioteca de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-340">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="03414-341">Esto es porque los diseños de biblioteca en función de las restricciones implícitas desconocidas o no estándares tienden a hacer que el código de usuario se conviertan en inflexibles y ligada al patrón de un marco de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="03414-341">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="03414-342">Además, hay una gran probabilidad de que un uso intensivo de las restricciones de miembro de esta manera puede dar lugar a tiempos de compilación mucho.</span><span class="sxs-lookup"><span data-stu-id="03414-342">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="03414-343">Definiciones de operador</span><span class="sxs-lookup"><span data-stu-id="03414-343">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="03414-344">Evite la definición de operadores simbólicos personalizados</span><span class="sxs-lookup"><span data-stu-id="03414-344">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="03414-345">Operadores personalizados son esenciales en algunas situaciones y dispositivos notacionales muy útiles dentro de un cuerpo grande del código de implementación.</span><span class="sxs-lookup"><span data-stu-id="03414-345">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="03414-346">Para los nuevos usuarios de una biblioteca, funciones con nombre son a menudo más fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="03414-346">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="03414-347">Además, operadores simbólicos personalizados pueden ser difíciles de documento y usuarios les resulta más difícil buscar ayuda sobre operadores, debido a las limitaciones existentes en los motores de IDE y búsqueda.</span><span class="sxs-lookup"><span data-stu-id="03414-347">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="03414-348">Como resultado, es mejor publicar su funcionalidad como funciones con nombre y miembros y además exponer operadores para esta funcionalidad solo si el beneficio notacional superan el costo cognitivo indica que existen y documentación.</span><span class="sxs-lookup"><span data-stu-id="03414-348">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="03414-349">Unidades de medida</span><span class="sxs-lookup"><span data-stu-id="03414-349">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="03414-350">Detenidamente utilizar unidades de medida de seguridad de tipos agregados en código de F #</span><span class="sxs-lookup"><span data-stu-id="03414-350">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="03414-351">Información de tipo adicional para unidades de medida se borra cuando se ve por otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-351">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="03414-352">Tenga en cuenta que reflexión, herramientas y componentes .NET verán tipos de redes SAN unidades.</span><span class="sxs-lookup"><span data-stu-id="03414-352">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="03414-353">Por ejemplo, verá los consumidores de C# `float` en lugar de `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="03414-353">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="03414-354">Abreviaturas de tipo</span><span class="sxs-lookup"><span data-stu-id="03414-354">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="03414-355">Utilizar con cuidado las abreviaturas de tipo para simplificar el código de F #</span><span class="sxs-lookup"><span data-stu-id="03414-355">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="03414-356">Reflexión, herramientas y componentes de .NET no podrán ver los nombres abreviados para los tipos.</span><span class="sxs-lookup"><span data-stu-id="03414-356">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="03414-357">Un uso significativo de abreviaturas de tipo también puede hacer que un dominio aparezca más complejo de lo es realmente, lo que podría confundir a los consumidores.</span><span class="sxs-lookup"><span data-stu-id="03414-357">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="03414-358">Evite las abreviaturas de tipo para los tipos públicos deben intrínsecamente diferentes a los que están disponibles en el tipo que se va a abreviar cuyos miembros y propiedades</span><span class="sxs-lookup"><span data-stu-id="03414-358">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="03414-359">En este caso, el tipo que se va a abreviar revela demasiado sobre la representación del tipo real que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="03414-359">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="03414-360">En su lugar, considere la posibilidad de ajustar la abreviatura en un tipo de clase o una unión discriminada de caso único (o bien, cuando el rendimiento es fundamental, considere el uso de un tipo de estructura que va a contener la abreviatura).</span><span class="sxs-lookup"><span data-stu-id="03414-360">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="03414-361">Por ejemplo, es tentador para definir una asignación múltiple como un caso especial de un mapa de F #, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="03414-361">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="03414-362">Sin embargo, las operaciones lógicas de notación de puntos de este tipo no son los mismos que las operaciones en un mapa: por ejemplo, resulta razonable de que el operador de búsqueda están asignados. [clave] devuelve la lista vacía si la clave no está en el diccionario, en lugar de cuando se genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="03414-362">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="03414-363">Directrices para las bibliotecas para su uso desde otros lenguajes de .NET</span><span class="sxs-lookup"><span data-stu-id="03414-363">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="03414-364">Cuando diseñe bibliotecas para usarlas en otros lenguajes. NET, es importante cumplir con la [instrucciones de diseño de biblioteca de .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="03414-364">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="03414-365">En este documento, estas bibliotecas se etiquetan como vainilla bibliotecas de. NET, en lugar de F #-orientada hacia las bibliotecas que usen F # construye sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="03414-365">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="03414-366">Diseñar vainilla bibliotecas de .NET significa proporciona las API conocidas e idiomáticas coherentes con el resto de .NET Framework, pues minimiza el uso de F #-construcciones específicas de la API pública.</span><span class="sxs-lookup"><span data-stu-id="03414-366">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="03414-367">Las reglas se explican en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="03414-367">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-sesign-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="03414-368">Sesign Namespace y el tipo (para las bibliotecas para su uso desde otros lenguajes. NET)</span><span class="sxs-lookup"><span data-stu-id="03414-368">Namespace and Type sesign (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="03414-369">Las convenciones de nomenclatura de .NET se aplican a la API pública de los componentes</span><span class="sxs-lookup"><span data-stu-id="03414-369">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="03414-370">Preste especial atención al uso de abreviaturas de nombres y las directrices de uso de mayúsculas. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-370">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="03414-371">Usar espacios de nombres, tipos y miembros como la estructura organizativa principal para los componentes de</span><span class="sxs-lookup"><span data-stu-id="03414-371">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="03414-372">Todos los archivos que contiene la funcionalidad pública deben comenzar por un `namespace` declaración y las únicas entidades orientados al público en espacios de nombres deben ser tipos.</span><span class="sxs-lookup"><span data-stu-id="03414-372">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="03414-373">No utilice los módulos de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-373">Do not use F# modules.</span></span>

<span data-ttu-id="03414-374">Utilizar módulos de no públicos para contener código de implementación, utilidad tipos y funciones de utilidad.</span><span class="sxs-lookup"><span data-stu-id="03414-374">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="03414-375">Los tipos estáticos debe preferirse sobre módulos, ya que permiten para la futura evolución de la API para usar la sobrecarga y otros conceptos de diseño de API de .NET que no se pueden usar dentro de los módulos de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-375">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="03414-376">Por ejemplo, en lugar de la API pública de la siguiente:</span><span class="sxs-lookup"><span data-stu-id="03414-376">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="03414-377">Tenga en cuenta en su lugar:</span><span class="sxs-lookup"><span data-stu-id="03414-377">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="03414-378">Usar tipos de registro de F # en las API de .NET de vainilla si el diseño de los tipos no evolucionar</span><span class="sxs-lookup"><span data-stu-id="03414-378">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="03414-379">Tipos de registro de F # se compilan en una clase simple de. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-379">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="03414-380">Estos son idóneos para algunos tipos simples, estables en las API.</span><span class="sxs-lookup"><span data-stu-id="03414-380">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="03414-381">Puede utilizar el `[<NoEquality>]` y `[<NoComparison>]` atributos para suprimir la generación automática de interfaces.</span><span class="sxs-lookup"><span data-stu-id="03414-381">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="03414-382">Además, evite usar campos de registro mutable de vainilla las API de .NET como estos expone un campo público.</span><span class="sxs-lookup"><span data-stu-id="03414-382">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="03414-383">Siempre tenga en cuenta si una clase proporcionaría una opción más flexible para la futura evolución de la API.</span><span class="sxs-lookup"><span data-stu-id="03414-383">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="03414-384">Por ejemplo, el siguiente código de F # expone la API pública a un consumidor de C#:</span><span class="sxs-lookup"><span data-stu-id="03414-384">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="03414-385">F #:</span><span class="sxs-lookup"><span data-stu-id="03414-385">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="03414-386">C#:</span><span class="sxs-lookup"><span data-stu-id="03414-386">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="03414-387">Ocultar la representación de tipos de unión de F # en las API de .NET de vainilla</span><span class="sxs-lookup"><span data-stu-id="03414-387">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="03414-388">Tipos de unión de F # no se usan habitualmente en los límites del componente, incluso para F #-a-F # de codificación.</span><span class="sxs-lookup"><span data-stu-id="03414-388">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="03414-389">Son un dispositivo de implementación excelente cuando se utiliza internamente en componentes y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="03414-389">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="03414-390">Al diseñar una API de .NET de vainilla, considere la posibilidad de ocultar la representación de un tipo de unión mediante una declaración privada o un archivo de signatura.</span><span class="sxs-lookup"><span data-stu-id="03414-390">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="03414-391">También puede aumentar los tipos que usan una representación en forma de unión internamente con miembros para proporcionar un deseado. API de NET orientado.</span><span class="sxs-lookup"><span data-stu-id="03414-391">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="03414-392">Diseño de interfaz gráfica de usuario y otros componentes por medio de los patrones de diseño de framework</span><span class="sxs-lookup"><span data-stu-id="03414-392">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="03414-393">Hay muchos marcos de trabajo diferentes dentro de. NET, como formularios Windows Forms, WPF y ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="03414-393">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="03414-394">Convenciones de nomenclatura y diseño para cada uno de ellos deben utilizarse si va a diseñar componentes para su uso en estos marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="03414-394">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="03414-395">Por ejemplo, para la programación en WPF, adopte patrones de diseño WPF para las clases que se está diseñando.</span><span class="sxs-lookup"><span data-stu-id="03414-395">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="03414-396">Para los modelos de programación de la interfaz de usuario, utilizar modelos de diseño como los eventos y colecciones basadas en notificaciones como los que se encuentran en <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="03414-396">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="03414-397">Diseño de objeto y el miembro (para las bibliotecas para su uso desde otros lenguajes. NET)</span><span class="sxs-lookup"><span data-stu-id="03414-397">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="03414-398">Usar CLIEvent (atributo) para exponer los eventos de .NET</span><span class="sxs-lookup"><span data-stu-id="03414-398">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="03414-399">Construir un `DelegateEvent` con .NET específicos de tipo que toma un objeto de delegado y `EventArgs` (en lugar de un `Event`, que simplemente utiliza el `FSharpHandler` tipo de forma predeterminada) para que los eventos se publican en la forma familiar de otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-399">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="03414-400">Exponer operaciones asincrónicas como métodos que devuelven las tareas de .NET</span><span class="sxs-lookup"><span data-stu-id="03414-400">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="03414-401">Las tareas se usan en .NET para representar los cálculos asincrónicos activos.</span><span class="sxs-lookup"><span data-stu-id="03414-401">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="03414-402">Las tareas son en general menos composicional que F # `Async<T>` objetos, ya que representan tareas "ya está ejecutando" y no pueden estar compuestos juntos de forma que realizar la composición paralelo o que ocultar la propagación de señales de cancelación y otros parámetros contextuales.</span><span class="sxs-lookup"><span data-stu-id="03414-402">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="03414-403">Sin embargo, a pesar de ello, los métodos que devuelven las tareas son la representación estándar de la programación asincrónica en .NET.</span><span class="sxs-lookup"><span data-stu-id="03414-403">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="03414-404">Que se van a menudo también va a aceptar un token de cancelación explícita:</span><span class="sxs-lookup"><span data-stu-id="03414-404">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="03414-405">Usar tipos de delegado de .NET en lugar de tipos de función de F #</span><span class="sxs-lookup"><span data-stu-id="03414-405">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="03414-406">Aquí "tipos de función de F #" significan que los tipos de "flecha" como `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="03414-406">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="03414-407">En lugar de esto:</span><span class="sxs-lookup"><span data-stu-id="03414-407">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="03414-408">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03414-408">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="03414-409">El tipo de función de F # aparece como `class FSharpFunc<T,U>` a otros lenguajes. NET y es menos adecuado para las características del lenguaje y herramientas que entender los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="03414-409">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="03414-410">Al crear un método de orden superior como destino .NET Framework 3.5 o superior, el `System.Func` y `System.Action` los delegados son las API derecho a publicar para permitir que los desarrolladores de .NET usar estas API en forma de baja fricción.</span><span class="sxs-lookup"><span data-stu-id="03414-410">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="03414-411">(Cuando el destino es .NET Framework 2.0, los tipos de delegado definido por el sistema son más limitados; considere el uso de los tipos de delegado predefinido, como `System.Converter<T,U>` o definir un tipo delegado específico.)</span><span class="sxs-lookup"><span data-stu-id="03414-411">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="03414-412">En el otro lado, los delegados de .NET no son naturales para F #-orientada hacia el bibliotecas (vea la sección siguiente sobre F #-orientada hacia el bibliotecas).</span><span class="sxs-lookup"><span data-stu-id="03414-412">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="03414-413">Como resultado, una estrategia de implementación habitual al desarrollar métodos de orden superior para las bibliotecas de .NET vainilla es cree todas la implementación mediante los tipos de función de F # y, a continuación, la API pública mediante delegados como una fachada fina sobre la real de F # implementación de.</span><span class="sxs-lookup"><span data-stu-id="03414-413">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="03414-414">Usar el patrón TryGetValue en lugar de devolver los valores de opción de F # y prefiere sobrecargar el método que toma los valores de opción de F # como argumentos</span><span class="sxs-lookup"><span data-stu-id="03414-414">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="03414-415">Patrones comunes de uso para el tipo de opción de F # en las API son mejores implementado en vainilla técnicas de diseño de las API de .NET con .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="03414-415">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="03414-416">En lugar de devolver un valor de opción de F #, considere la posibilidad de usar el tipo de valor devuelto bool suma un parámetro de salida como se muestra en el patrón "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="03414-416">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="03414-417">Y, en lugar de tomar valores de opción de F # como parámetros, considere el uso de la sobrecarga de métodos o argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="03414-417">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="03414-418">Utilice la interfaz de colección de .NET tipos IEnumerable\<T\> y IDictionary\<clave, valor\> para parámetros y valores devueltos</span><span class="sxs-lookup"><span data-stu-id="03414-418">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="03414-419">Evite el uso de tipos de colección concretos, como matrices de .NET `T[]`, tipos de F # `list<T>`, `Map<Key,Value>` y `Set<T>`, y tipos de colección concretos. NET, como `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="03414-419">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="03414-420">Las instrucciones de diseño de la biblioteca de .NET tienen un buen consejo acerca de cuándo se utilizan varios tipos de colección como `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="03414-420">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="03414-421">Algunos uso de matrices (`T[]`) es aceptable en algunos casos, por motivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="03414-421">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="03414-422">Tenga en cuenta especialmente que `seq<T>` es simplemente la F # alias de `IEnumerable<T>`, y, por tanto, a menudo es un tipo adecuado para una API de .NET de vainilla seq.</span><span class="sxs-lookup"><span data-stu-id="03414-422">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="03414-423">En lugar de F # listas:</span><span class="sxs-lookup"><span data-stu-id="03414-423">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="03414-424">Usar secuencias de F #:</span><span class="sxs-lookup"><span data-stu-id="03414-424">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="03414-425">Utilice el tipo de unidad como el único tipo de entrada de un método para definir un método de argumento de cero, o como el único tipo para definir un método que devuelve void de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="03414-425">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="03414-426">Evite otros usos del tipo de unidad.</span><span class="sxs-lookup"><span data-stu-id="03414-426">Avoid other uses of the unit type.</span></span> <span data-ttu-id="03414-427">Se trata de un buen:</span><span class="sxs-lookup"><span data-stu-id="03414-427">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="03414-428">Esto es incorrecto:</span><span class="sxs-lookup"><span data-stu-id="03414-428">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="03414-429">Comprobar si hay valores null en vainilla límites de API de .NET</span><span class="sxs-lookup"><span data-stu-id="03414-429">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="03414-430">Código de implementación de F # suele tener menos valores null, debido a los patrones de diseño inmutable y las restricciones en el uso de los literales null para tipos de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-430">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="03414-431">Otros lenguajes de .NET a menudo utilizan null como un valor mucha más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="03414-431">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="03414-432">Por este motivo, código de F # que expone una API de .NET de vainilla debe comprobar los parámetros si hay valores null en el límite de API y evitar que estos valores fluyendo más profunda en el código de implementación de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-432">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="03414-433">El `isNull` función o coincidencia de patrones en el `null` puede utilizar el modelo.</span><span class="sxs-lookup"><span data-stu-id="03414-433">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="03414-434">Evite el uso de tuplas como valores devueltos</span><span class="sxs-lookup"><span data-stu-id="03414-434">Avoid using tuples as return values</span></span>

<span data-ttu-id="03414-435">En su lugar, preferible devolver un tipo con nombre que contiene los datos agregados o usar los parámetros de salida para devolver varios valores.</span><span class="sxs-lookup"><span data-stu-id="03414-435">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="03414-436">Si bien existen tuplas y struct tuplas en .NET (incluida la compatibilidad de lenguaje C# para struct tuplas), con mayor frecuencia no proporcionará la API ideal y esperada para los desarrolladores de .NET.</span><span class="sxs-lookup"><span data-stu-id="03414-436">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="03414-437">Evite el uso de la currificación de parámetros</span><span class="sxs-lookup"><span data-stu-id="03414-437">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="03414-438">En su lugar, use .NET convenciones de llamada ``Method(arg1,arg2,…,argN)``.</span><span class="sxs-lookup"><span data-stu-id="03414-438">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="03414-439">Sugerencia: Si está diseñando bibliotecas para usarlas desde cualquier lenguaje. NET, a continuación, no hay ningún sustituto para hacer realidad algunos experimental C# y Visual Basic de programación para asegurarse de que las bibliotecas "apariencia derecha" de estos lenguajes.</span><span class="sxs-lookup"><span data-stu-id="03414-439">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="03414-440">También puede usar herramientas como .NET Reflector y el Examinador de objetos de Visual Studio para asegurarse de que su documentación y las bibliotecas de aparecen como se esperaba a los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="03414-440">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="03414-441">Apéndice</span><span class="sxs-lookup"><span data-stu-id="03414-441">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="03414-442">Ejemplo to-end del diseño de código de F # para su uso por otros lenguajes de .NET</span><span class="sxs-lookup"><span data-stu-id="03414-442">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="03414-443">Tenga en cuenta la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="03414-443">Consider the following class:</span></span>

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

<span data-ttu-id="03414-444">El tipo F # deducido de esta clase es como sigue:</span><span class="sxs-lookup"><span data-stu-id="03414-444">The inferred F# type of this class is as follows:</span></span>

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

<span data-ttu-id="03414-445">¡Eche un vistazo a cómo aparece este tipo de F # para un programador que use otro lenguaje. NET.</span><span class="sxs-lookup"><span data-stu-id="03414-445">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="03414-446">Por ejemplo, aproximado C# "firma" es como sigue:</span><span class="sxs-lookup"><span data-stu-id="03414-446">For example, the approximate C# “signature” is as follows:</span></span>

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="03414-447">Hay algunas cuestiones importantes deben tener en cuenta cómo F # representa construcciones aquí.</span><span class="sxs-lookup"><span data-stu-id="03414-447">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="03414-448">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="03414-448">For example:</span></span>

* <span data-ttu-id="03414-449">Se ha conservado los metadatos como nombres de argumento.</span><span class="sxs-lookup"><span data-stu-id="03414-449">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="03414-450">F # métodos que toman dos argumentos se convierten en métodos de C# que toman dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="03414-450">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="03414-451">Las funciones y las listas se convierten en las referencias a los tipos correspondientes en la biblioteca de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-451">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="03414-452">El código siguiente muestra cómo ajustar este código para aprovechar todo esto en cuenta.</span><span class="sxs-lookup"><span data-stu-id="03414-452">The following code shows how to adjust this code to take these things into account.</span></span>

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

<span data-ttu-id="03414-453">El tipo F # deducido del código es como sigue:</span><span class="sxs-lookup"><span data-stu-id="03414-453">The inferred F# type of the code is as follows:</span></span>

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

<span data-ttu-id="03414-454">La firma de C# ahora es como sigue:</span><span class="sxs-lookup"><span data-stu-id="03414-454">The C# signature is now as follows:</span></span>

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="03414-455">Las correcciones realizan preparar este tipo para su uso como parte de una biblioteca .NET vainilla son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="03414-455">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="03414-456">Ajustar varios nombres: `Point1`, `n`, `l`, y `f` pasara a ser `RadialPoint`, `count`, `factor`, y `transform`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="03414-456">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="03414-457">Usa un tipo de valor devuelto de `seq<RadialPoint>` en lugar de `RadialPoint list` cambiando una construcción de lista mediante `[ ... ]` a una secuencia de la construcción utilizando `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="03414-457">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="03414-458">Usa el tipo de delegado .NET `System.Func` en lugar de un tipo de función de F #.</span><span class="sxs-lookup"><span data-stu-id="03414-458">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="03414-459">Esto hace mucho más adecuada consumir en código C#.</span><span class="sxs-lookup"><span data-stu-id="03414-459">This makes it far nicer to consume in C# code.</span></span>
