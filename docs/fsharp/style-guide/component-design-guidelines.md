---
title: Instrucciones de diseño de componentes de F#
description: 'Obtenga información sobre las directrices para escribir componentes de F # destinados a su consumo por otros llamadores.'
ms.date: 05/14/2018
ms.openlocfilehash: 590bda0660d54ea73c590d31e694f3d499e0fd9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209141"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="19be2-103">Instrucciones de diseño de componentes de F#</span><span class="sxs-lookup"><span data-stu-id="19be2-103">F# component design guidelines</span></span>

<span data-ttu-id="19be2-104">Este documento es un conjunto de directrices de diseño de componentes para la programación en F #, en función de las instrucciones de diseño de componentes de F #, V14, Microsoft Research y una versión que originalmente se seleccionada y mantiene con F # Software Foundation.</span><span class="sxs-lookup"><span data-stu-id="19be2-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and a version that was originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="19be2-105">En este documento se supone que está familiarizado con la programación en F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="19be2-106">Muchas gracias a la comunidad de F # por sus contribuciones e información útil sobre las distintas versiones de esta guía.</span><span class="sxs-lookup"><span data-stu-id="19be2-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="19be2-107">Información general</span><span class="sxs-lookup"><span data-stu-id="19be2-107">Overview</span></span>

<span data-ttu-id="19be2-108">En este documento se analizan algunos de los problemas relacionados con el diseño y la codificación de componentes de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="19be2-109">Un componente puede significar cualquiera de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="19be2-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="19be2-110">Una capa del proyecto de F # que tiene consumidores externos dentro de ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="19be2-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="19be2-111">Biblioteca diseñada para el consumo por código de F # a través de los límites del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19be2-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="19be2-112">Biblioteca diseñada para su consumo por cualquier lenguaje .NET a través de los límites de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="19be2-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="19be2-113">Biblioteca diseñada para su distribución a través de un repositorio de paquetes, como [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="19be2-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="19be2-114">Las técnicas descritas en este artículo siguen los [cinco principios de buen código de F #](index.md#five-principles-of-good-f-code)y, por tanto, usan la programación funcional y de objetos según corresponda.</span><span class="sxs-lookup"><span data-stu-id="19be2-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="19be2-115">Independientemente de la metodología, el diseñador de componentes y bibliotecas se enfrenta a una serie de problemas prácticos y prosaics al intentar crear una API que es más fácil de usar para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="19be2-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="19be2-116">La aplicación Conscientious de las instrucciones de diseño de la [biblioteca de .net](../../standard/design-guidelines/index.md) le dirigirá a la creación de un conjunto coherente de API que son agradables de consumir.</span><span class="sxs-lookup"><span data-stu-id="19be2-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="19be2-117">Directrices generales</span><span class="sxs-lookup"><span data-stu-id="19be2-117">General guidelines</span></span>

<span data-ttu-id="19be2-118">Hay algunas directrices universales que se aplican a las bibliotecas de F #, independientemente de la audiencia prevista para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="19be2-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="19be2-119">Obtener información sobre las directrices de diseño de la biblioteca .NET</span><span class="sxs-lookup"><span data-stu-id="19be2-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="19be2-120">Independientemente del tipo de código de F # que esté haciendo, es útil tener conocimientos prácticos de las instrucciones de diseño de la [biblioteca de .net](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="19be2-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="19be2-121">La mayoría de los programadores de F # y .NET estarán familiarizados con estas directrices y esperamos que el código .NET se ajuste a ellos.</span><span class="sxs-lookup"><span data-stu-id="19be2-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="19be2-122">Las instrucciones de diseño de la biblioteca de .NET proporcionan instrucciones generales sobre la nomenclatura, el diseño de clases e interfaces, el diseño de miembros (propiedades, métodos, eventos, etc.) y otros, y son un primer punto de referencia útil para una variedad de instrucciones de diseño.</span><span class="sxs-lookup"><span data-stu-id="19be2-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="19be2-123">Agregar comentarios de documentación XML al código</span><span class="sxs-lookup"><span data-stu-id="19be2-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="19be2-124">La documentación XML de las API públicas garantiza que los usuarios puedan obtener grandes IntelliSense y QuickInfo al usar estos tipos y miembros, y habilitar la creación de archivos de documentación para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="19be2-124">XML documentation on public APIs ensures that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="19be2-125">Consulte la [documentación XML](../language-reference/xml-documentation.md) sobre las distintas etiquetas XML que se pueden usar para el marcado adicional en los comentarios de XmlDoc.</span><span class="sxs-lookup"><span data-stu-id="19be2-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

<span data-ttu-id="19be2-126">Puede usar los comentarios XML de forma corta ( `/// comment` ) o los comentarios XML estándar ( `///<summary>comment</summary>` ).</span><span class="sxs-lookup"><span data-stu-id="19be2-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="19be2-127">Considere la posibilidad de usar archivos de signatura explícitos (. FSI) para la biblioteca estable y las API de componentes</span><span class="sxs-lookup"><span data-stu-id="19be2-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="19be2-128">El uso de archivos de firmas explícitos en una biblioteca de F # proporciona un resumen conciso de la API pública, lo que ayuda a garantizar que conoce la superficie pública completa de la biblioteca y proporciona una separación limpia entre la documentación pública y los detalles internos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="19be2-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which helps to ensure that you know the full public surface of your library, and provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="19be2-129">Los archivos de signatura agregan fricción al cambio de la API pública, ya que requieren que se realicen cambios en los archivos de implementación y de firma.</span><span class="sxs-lookup"><span data-stu-id="19be2-129">Signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="19be2-130">Como resultado, los archivos de firma normalmente solo deben introducirse cuando una API se ha contratado y ya no se espera que cambie de forma significativa.</span><span class="sxs-lookup"><span data-stu-id="19be2-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="19be2-131">Siga siempre los procedimientos recomendados para el uso de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="19be2-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="19be2-132">Siga las [prácticas recomendadas para usar cadenas en la guía de .net](../../standard/base-types/best-practices-strings.md) .</span><span class="sxs-lookup"><span data-stu-id="19be2-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="19be2-133">En concreto, indique siempre explícitamente el *objetivo cultural* en la conversión y la comparación de cadenas (si procede).</span><span class="sxs-lookup"><span data-stu-id="19be2-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="19be2-134">Directrices para las bibliotecas orientadas a F #</span><span class="sxs-lookup"><span data-stu-id="19be2-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="19be2-135">En esta sección se presentan recomendaciones para el desarrollo de bibliotecas públicas con conexión a F #. es decir, las bibliotecas exponen las API públicas que están pensadas para que las usen los desarrolladores de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="19be2-136">Hay una variedad de recomendaciones de diseño de biblioteca que se aplican específicamente a F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="19be2-137">En ausencia de las recomendaciones específicas que se indican a continuación, las instrucciones de diseño de la biblioteca de .NET son la guía de reserva.</span><span class="sxs-lookup"><span data-stu-id="19be2-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="19be2-138">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="19be2-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="19be2-139">Usar convenciones de mayúsculas y minúsculas de nomenclatura .NET</span><span class="sxs-lookup"><span data-stu-id="19be2-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="19be2-140">En la tabla siguiente se siguen las convenciones de nomenclatura y capitalización de .NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="19be2-141">Hay pequeñas adiciones que también incluyen construcciones de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="19be2-142">Construcción</span><span class="sxs-lookup"><span data-stu-id="19be2-142">Construct</span></span> | <span data-ttu-id="19be2-143">Caso</span><span class="sxs-lookup"><span data-stu-id="19be2-143">Case</span></span> | <span data-ttu-id="19be2-144">Parte</span><span class="sxs-lookup"><span data-stu-id="19be2-144">Part</span></span> | <span data-ttu-id="19be2-145">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="19be2-145">Examples</span></span> | <span data-ttu-id="19be2-146">Notas</span><span class="sxs-lookup"><span data-stu-id="19be2-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="19be2-147">Tipos concretos</span><span class="sxs-lookup"><span data-stu-id="19be2-147">Concrete types</span></span> | <span data-ttu-id="19be2-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-148">PascalCase</span></span> | <span data-ttu-id="19be2-149">Nombre/Adjetivo</span><span class="sxs-lookup"><span data-stu-id="19be2-149">Noun/ adjective</span></span> | <span data-ttu-id="19be2-150">Lista, doble, complejo</span><span class="sxs-lookup"><span data-stu-id="19be2-150">List, Double, Complex</span></span> | <span data-ttu-id="19be2-151">Los tipos concretos son Structs, clases, enumeraciones, delegados, registros y uniones.</span><span class="sxs-lookup"><span data-stu-id="19be2-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="19be2-152">Aunque los nombres de tipo están tradicionalmente en minúsculas en OCaml, F # ha adoptado el esquema de nomenclatura de .NET para los tipos.</span><span class="sxs-lookup"><span data-stu-id="19be2-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="19be2-153">DLL</span><span class="sxs-lookup"><span data-stu-id="19be2-153">DLLs</span></span>           | <span data-ttu-id="19be2-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-154">PascalCase</span></span> |                 | <span data-ttu-id="19be2-155">Fabrikam. Core. dll</span><span class="sxs-lookup"><span data-stu-id="19be2-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="19be2-156">Etiquetas de Unión</span><span class="sxs-lookup"><span data-stu-id="19be2-156">Union tags</span></span>     | <span data-ttu-id="19be2-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-157">PascalCase</span></span> | <span data-ttu-id="19be2-158">Nombre</span><span class="sxs-lookup"><span data-stu-id="19be2-158">Noun</span></span> | <span data-ttu-id="19be2-159">Algunos, agregar, correcto</span><span class="sxs-lookup"><span data-stu-id="19be2-159">Some, Add, Success</span></span> | <span data-ttu-id="19be2-160">No use un prefijo en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="19be2-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="19be2-161">Opcionalmente, use un prefijo cuando sea interno, como`type Teams = TAlpha | TBeta | TDelta.`</span><span class="sxs-lookup"><span data-stu-id="19be2-161">Optionally use a prefix when internal, such as `type Teams = TAlpha | TBeta | TDelta.`</span></span> |
| <span data-ttu-id="19be2-162">Evento</span><span class="sxs-lookup"><span data-stu-id="19be2-162">Event</span></span>          | <span data-ttu-id="19be2-163">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-163">PascalCase</span></span> | <span data-ttu-id="19be2-164">Verbo</span><span class="sxs-lookup"><span data-stu-id="19be2-164">Verb</span></span> | <span data-ttu-id="19be2-165">ValueChanged/ValueChanging</span><span class="sxs-lookup"><span data-stu-id="19be2-165">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="19be2-166">Excepciones</span><span class="sxs-lookup"><span data-stu-id="19be2-166">Exceptions</span></span>     | <span data-ttu-id="19be2-167">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-167">PascalCase</span></span> |      | <span data-ttu-id="19be2-168">WebException</span><span class="sxs-lookup"><span data-stu-id="19be2-168">WebException</span></span> | <span data-ttu-id="19be2-169">El nombre debe terminar con "Exception".</span><span class="sxs-lookup"><span data-stu-id="19be2-169">Name should end with "Exception".</span></span> |
| <span data-ttu-id="19be2-170">Campo</span><span class="sxs-lookup"><span data-stu-id="19be2-170">Field</span></span>          | <span data-ttu-id="19be2-171">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-171">PascalCase</span></span> | <span data-ttu-id="19be2-172">Nombre</span><span class="sxs-lookup"><span data-stu-id="19be2-172">Noun</span></span> | <span data-ttu-id="19be2-173">CurrentName</span><span class="sxs-lookup"><span data-stu-id="19be2-173">CurrentName</span></span>  | |
| <span data-ttu-id="19be2-174">Tipos de interfaz</span><span class="sxs-lookup"><span data-stu-id="19be2-174">Interface types</span></span> |  <span data-ttu-id="19be2-175">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-175">PascalCase</span></span> | <span data-ttu-id="19be2-176">Nombre/Adjetivo</span><span class="sxs-lookup"><span data-stu-id="19be2-176">Noun/ adjective</span></span> | <span data-ttu-id="19be2-177">IDisposable</span><span class="sxs-lookup"><span data-stu-id="19be2-177">IDisposable</span></span> | <span data-ttu-id="19be2-178">El nombre debe comenzar por "I".</span><span class="sxs-lookup"><span data-stu-id="19be2-178">Name should start with "I".</span></span> |
| <span data-ttu-id="19be2-179">Método</span><span class="sxs-lookup"><span data-stu-id="19be2-179">Method</span></span> |  <span data-ttu-id="19be2-180">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-180">PascalCase</span></span> |  <span data-ttu-id="19be2-181">Verbo</span><span class="sxs-lookup"><span data-stu-id="19be2-181">Verb</span></span> | <span data-ttu-id="19be2-182">ToString</span><span class="sxs-lookup"><span data-stu-id="19be2-182">ToString</span></span> | |
| <span data-ttu-id="19be2-183">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="19be2-183">Namespace</span></span> | <span data-ttu-id="19be2-184">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-184">PascalCase</span></span> | | <span data-ttu-id="19be2-185"> Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="19be2-185">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="19be2-186">Por lo general `<Organization>.<Technology>[.<Subnamespace>]` , use, aunque Quite la organización si la tecnología es independiente de la organización.</span><span class="sxs-lookup"><span data-stu-id="19be2-186">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="19be2-187">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19be2-187">Parameters</span></span> | <span data-ttu-id="19be2-188">camelCase</span><span class="sxs-lookup"><span data-stu-id="19be2-188">camelCase</span></span> | <span data-ttu-id="19be2-189">Nombre</span><span class="sxs-lookup"><span data-stu-id="19be2-189">Noun</span></span> |  <span data-ttu-id="19be2-190">typeName, transformación, intervalo</span><span class="sxs-lookup"><span data-stu-id="19be2-190">typeName, transform, range</span></span> | |
| <span data-ttu-id="19be2-191">permitir valores (interno)</span><span class="sxs-lookup"><span data-stu-id="19be2-191">let values (internal)</span></span> | <span data-ttu-id="19be2-192">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-192">camelCase or PascalCase</span></span> | <span data-ttu-id="19be2-193">Nombre/verbo</span><span class="sxs-lookup"><span data-stu-id="19be2-193">Noun/ verb</span></span> |  <span data-ttu-id="19be2-194">getValue, MyTable</span><span class="sxs-lookup"><span data-stu-id="19be2-194">getValue, myTable</span></span> |
| <span data-ttu-id="19be2-195">permitir valores (externos)</span><span class="sxs-lookup"><span data-stu-id="19be2-195">let values (external)</span></span> | <span data-ttu-id="19be2-196">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-196">camelCase or PascalCase</span></span> | <span data-ttu-id="19be2-197">Nombre/verbo</span><span class="sxs-lookup"><span data-stu-id="19be2-197">Noun/verb</span></span>  | <span data-ttu-id="19be2-198">List. map, fechas. hoy</span><span class="sxs-lookup"><span data-stu-id="19be2-198">List.map, Dates.Today</span></span> | <span data-ttu-id="19be2-199">los valores de Let enlazados suelen ser públicos cuando se siguen los patrones de diseño funcionales tradicionales.</span><span class="sxs-lookup"><span data-stu-id="19be2-199">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="19be2-200">Sin embargo, por lo general, se usa PascalCase cuando el identificador se puede usar desde otros lenguajes .NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-200">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="19be2-201">Propiedad</span><span class="sxs-lookup"><span data-stu-id="19be2-201">Property</span></span>  | <span data-ttu-id="19be2-202">PascalCase</span><span class="sxs-lookup"><span data-stu-id="19be2-202">PascalCase</span></span>  | <span data-ttu-id="19be2-203">Nombre/Adjetivo</span><span class="sxs-lookup"><span data-stu-id="19be2-203">Noun/ adjective</span></span>  | <span data-ttu-id="19be2-204">IsEndOfFile, BackColor</span><span class="sxs-lookup"><span data-stu-id="19be2-204">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="19be2-205">Normalmente, las propiedades booleanas usan es y pueden y deben ser afirmativas, como en IsEndOfFile, no IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="19be2-205">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="19be2-206">Evitar abreviaturas</span><span class="sxs-lookup"><span data-stu-id="19be2-206">Avoid abbreviations</span></span>

<span data-ttu-id="19be2-207">Las instrucciones de .NET desaconsejan el uso de abreviaturas (por ejemplo, "usar `OnButtonClick` en lugar de `OnBtnClick` ").</span><span class="sxs-lookup"><span data-stu-id="19be2-207">The .NET guidelines discourage the use of abbreviations (for example, "use `OnButtonClick` rather than `OnBtnClick`").</span></span> <span data-ttu-id="19be2-208">Se toleran las abreviaturas comunes, como `Async` "asincrónicas".</span><span class="sxs-lookup"><span data-stu-id="19be2-208">Common abbreviations, such as `Async` for "Asynchronous", are tolerated.</span></span> <span data-ttu-id="19be2-209">A veces, esta instrucción se omite en la programación funcional; por ejemplo, `List.iter` usa una abreviatura para "iterar".</span><span class="sxs-lookup"><span data-stu-id="19be2-209">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for "iterate".</span></span> <span data-ttu-id="19be2-210">Por esta razón, el uso de abreviaturas tiende a tolerar un mayor grado en la programación de F # a F #, pero normalmente se debe evitar en el diseño de componentes públicos.</span><span class="sxs-lookup"><span data-stu-id="19be2-210">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="19be2-211">Evitar conflictos de nombres con mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="19be2-211">Avoid casing name collisions</span></span>

<span data-ttu-id="19be2-212">Las directrices de .NET indican que no se puede usar con mayúsculas y minúsculas para eliminar la ambigüedad de los conflictos de nombres, ya que algunos lenguajes de cliente (por ejemplo, Visual Basic) no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="19be2-212">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="19be2-213">Usar acrónimos cuando corresponda</span><span class="sxs-lookup"><span data-stu-id="19be2-213">Use acronyms where appropriate</span></span>

<span data-ttu-id="19be2-214">Los acrónimos como XML no son abreviaturas y se usan ampliamente en las bibliotecas de .NET en formato inversado (XML).</span><span class="sxs-lookup"><span data-stu-id="19be2-214">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="19be2-215">Solo se deben usar acrónimos conocidos y ampliamente reconocidos.</span><span class="sxs-lookup"><span data-stu-id="19be2-215">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="19be2-216">Usar PascalCase para nombres de parámetros genéricos</span><span class="sxs-lookup"><span data-stu-id="19be2-216">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="19be2-217">Use PascalCase para los nombres de parámetros genéricos en las API públicas, incluidas las bibliotecas orientadas a F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-217">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="19be2-218">En concreto, use nombres como `T` , `U` , `T1` , `T2` para los parámetros genéricos arbitrarios y, cuando tengan sentido los nombres específicos, en el caso de las bibliotecas orientadas a F #, use nombres como `Key` , `Value` , `Arg` (pero no por ejemplo `TKey` ).</span><span class="sxs-lookup"><span data-stu-id="19be2-218">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="19be2-219">Uso de PascalCase o camelCase para funciones y valores públicos en módulos de F #</span><span class="sxs-lookup"><span data-stu-id="19be2-219">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="19be2-220">camelCase se usa para las funciones públicas que están diseñadas para usarse sin calificar (por ejemplo, `invalidArg` ) y para las "funciones de colección estándar" (por ejemplo, List. map).</span><span class="sxs-lookup"><span data-stu-id="19be2-220">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the "standard collection functions" (for example, List.map).</span></span> <span data-ttu-id="19be2-221">En ambos casos, los nombres de función actúan de forma muy parecida a las palabras clave en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="19be2-221">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="19be2-222">Diseño de objetos, tipos y módulos</span><span class="sxs-lookup"><span data-stu-id="19be2-222">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="19be2-223">Usar espacios de nombres o módulos para contener los tipos y módulos</span><span class="sxs-lookup"><span data-stu-id="19be2-223">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="19be2-224">Cada archivo de F # de un componente debe comenzar con una declaración de espacio de nombres o una declaración de módulo.</span><span class="sxs-lookup"><span data-stu-id="19be2-224">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="19be2-225">or</span><span class="sxs-lookup"><span data-stu-id="19be2-225">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="19be2-226">Las diferencias entre el uso de módulos y espacios de nombres para organizar el código en el nivel superior son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="19be2-226">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="19be2-227">Los espacios de nombres pueden abarcar varios archivos</span><span class="sxs-lookup"><span data-stu-id="19be2-227">Namespaces can span multiple files</span></span>
* <span data-ttu-id="19be2-228">Los espacios de nombres no pueden contener funciones de F # a menos que estén dentro de un módulo interno</span><span class="sxs-lookup"><span data-stu-id="19be2-228">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="19be2-229">El código de cualquier módulo determinado debe estar incluido en un único archivo.</span><span class="sxs-lookup"><span data-stu-id="19be2-229">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="19be2-230">Los módulos de nivel superior pueden contener funciones de F # sin necesidad de un módulo interno</span><span class="sxs-lookup"><span data-stu-id="19be2-230">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="19be2-231">La elección entre un módulo o un espacio de nombres de nivel superior afecta al formulario compilado del código y, por tanto, afectará a la vista de otros lenguajes .NET en los casos en que la API se consuma fuera del código de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-231">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="19be2-232">Usar métodos y propiedades para operaciones intrínsecas a tipos de objeto</span><span class="sxs-lookup"><span data-stu-id="19be2-232">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="19be2-233">Al trabajar con objetos, es mejor asegurarse de que la funcionalidad consumible se implementa como métodos y propiedades en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="19be2-233">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="19be2-234">No es necesario implementar la mayor parte de la funcionalidad para un miembro determinado en ese miembro, pero la parte consumible de esa funcionalidad debe ser.</span><span class="sxs-lookup"><span data-stu-id="19be2-234">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="19be2-235">Usar clases para encapsular el estado mutable</span><span class="sxs-lookup"><span data-stu-id="19be2-235">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="19be2-236">En F #, esto solo se debe hacer si el estado no está encapsulado por otra construcción de lenguaje, como un cierre, una expresión de secuencia o un cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="19be2-236">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="19be2-237">Usar interfaces para agrupar operaciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="19be2-237">Use interfaces to group related operations</span></span>

<span data-ttu-id="19be2-238">Use los tipos de interfaz para representar un conjunto de operaciones.</span><span class="sxs-lookup"><span data-stu-id="19be2-238">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="19be2-239">Esto es preferible a otras opciones, como tuplas de funciones o registros de funciones.</span><span class="sxs-lookup"><span data-stu-id="19be2-239">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="19be2-240">En preferencia a:</span><span class="sxs-lookup"><span data-stu-id="19be2-240">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

<span data-ttu-id="19be2-241">Las interfaces son conceptos de primera clase en .NET, que puede usar para lograr lo que normalmente le daría.</span><span class="sxs-lookup"><span data-stu-id="19be2-241">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="19be2-242">Además, se pueden usar para codificar tipos existencial en el programa, que no pueden tener registros de funciones.</span><span class="sxs-lookup"><span data-stu-id="19be2-242">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a><span data-ttu-id="19be2-243">Usar un módulo para agrupar funciones que actúan en colecciones</span><span class="sxs-lookup"><span data-stu-id="19be2-243">Use a module to group functions that act on collections</span></span>

<span data-ttu-id="19be2-244">Al definir un tipo de colección, considere la posibilidad de proporcionar un conjunto estándar de operaciones como `CollectionType.map` y `CollectionType.iter` ) para los nuevos tipos de colección.</span><span class="sxs-lookup"><span data-stu-id="19be2-244">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="19be2-245">Si incluye este módulo, siga las convenciones de nomenclatura estándar para las funciones que se encuentran en FSharp. Core.</span><span class="sxs-lookup"><span data-stu-id="19be2-245">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="19be2-246">Usar un módulo para agrupar funciones para funciones canónicas comunes, especialmente en bibliotecas matemáticas y DSL</span><span class="sxs-lookup"><span data-stu-id="19be2-246">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="19be2-247">Por ejemplo, `Microsoft.FSharp.Core.Operators` es una colección abierta automáticamente de funciones de nivel superior (como `abs` y `sin` ) proporcionada por FSharp. Core. dll.</span><span class="sxs-lookup"><span data-stu-id="19be2-247">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="19be2-248">Del mismo modo, una biblioteca de estadísticas podría incluir un módulo con funciones `erf` y `erfc` , donde este módulo está diseñado para que se abra explícita o automáticamente.</span><span class="sxs-lookup"><span data-stu-id="19be2-248">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="19be2-249">Considere la posibilidad de usar RequireQualifiedAccess y aplicar cuidadosamente los atributos AutoOpen</span><span class="sxs-lookup"><span data-stu-id="19be2-249">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="19be2-250">Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que el módulo no se puede abrir y que las referencias a los elementos del módulo requieren un acceso calificado explícito.</span><span class="sxs-lookup"><span data-stu-id="19be2-250">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="19be2-251">Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.</span><span class="sxs-lookup"><span data-stu-id="19be2-251">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="19be2-252">Esto resulta útil cuando las funciones y los valores del módulo tienen nombres que es probable que entren en conflicto con los nombres de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="19be2-252">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="19be2-253">Requerir acceso cualificado puede aumentar considerablemente el mantenimiento a largo plazo y la evolución de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="19be2-253">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="19be2-254">Agregar el `[<AutoOpen>]` atributo a un módulo significa que el módulo se abrirá cuando se abra el espacio de nombres que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="19be2-254">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="19be2-255">El `[<AutoOpen>]` atributo también se puede aplicar a un ensamblado para indicar un módulo que se abre automáticamente cuando se hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19be2-255">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="19be2-256">Por ejemplo, una biblioteca de estadísticas **MathsHeaven. Statistics** puede contener una `module MathsHeaven.Statistics.Operators` función contenedora `erf` y `erfc` .</span><span class="sxs-lookup"><span data-stu-id="19be2-256">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="19be2-257">Es razonable marcar este módulo como `[<AutoOpen>]` .</span><span class="sxs-lookup"><span data-stu-id="19be2-257">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="19be2-258">Esto significa `open MathsHeaven.Statistics` que también abrirá este módulo y incluirá los nombres `erf` y `erfc` en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="19be2-258">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="19be2-259">Otro uso adecuado de `[<AutoOpen>]` es para los módulos que contienen métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="19be2-259">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="19be2-260">`[<AutoOpen>]`El uso excesivo de los clientes potenciales en los espacios de nombres contaminados y el atributo debe usarse con cuidado.</span><span class="sxs-lookup"><span data-stu-id="19be2-260">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="19be2-261">En el caso de bibliotecas específicas de dominios específicos, el uso prudente de `[<AutoOpen>]` puede dar lugar a una mejor facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="19be2-261">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="19be2-262">Considere la posibilidad de definir miembros de operador en clases en las que el uso de operadores Well-Knows sea adecuado.</span><span class="sxs-lookup"><span data-stu-id="19be2-262">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="19be2-263">A veces, las clases se utilizan para modelar construcciones matemáticas como vectores.</span><span class="sxs-lookup"><span data-stu-id="19be2-263">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="19be2-264">Cuando el dominio que se está modelando tiene operadores conocidos, es útil definirlos como miembros intrínsecos de la clase.</span><span class="sxs-lookup"><span data-stu-id="19be2-264">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="19be2-265">Esta guía se corresponde con las instrucciones generales de .NET para estos tipos.</span><span class="sxs-lookup"><span data-stu-id="19be2-265">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="19be2-266">Sin embargo, también puede ser importante en la codificación de F #, ya que permite usar estos tipos junto con funciones y métodos de F # con restricciones de miembro, como List. sumBy (.</span><span class="sxs-lookup"><span data-stu-id="19be2-266">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="19be2-267">Considere el uso de Compiledname (para proporcionar un. Nombre descriptivo para otros consumidores del lenguaje .NET</span><span class="sxs-lookup"><span data-stu-id="19be2-267">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="19be2-268">En ocasiones, es posible que desee asignar un nombre a algo en un estilo para los consumidores de F # (por ejemplo, un miembro estático en minúsculas para que aparezca como si fuera una función enlazada a un módulo), pero tener un estilo diferente para el nombre cuando se compila en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19be2-268">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="19be2-269">Puede usar el `[<CompiledName>]` atributo para proporcionar un estilo diferente para el código que no es de F # que usa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19be2-269">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="19be2-270">Mediante el uso de `[<CompiledName>]` , puede usar las convenciones de nomenclatura de .net para los consumidores que no son de F # del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19be2-270">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="19be2-271">Usar la sobrecarga de métodos para las funciones miembro, si esto proporciona una API más sencilla</span><span class="sxs-lookup"><span data-stu-id="19be2-271">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="19be2-272">La sobrecarga de métodos es una herramienta eficaz para simplificar una API que puede necesitar realizar una funcionalidad similar, pero con diferentes opciones o argumentos.</span><span class="sxs-lookup"><span data-stu-id="19be2-272">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="19be2-273">En F #, es más común sobrecargar el número de argumentos en lugar de los tipos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="19be2-273">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="19be2-274">Ocultar las representaciones de los tipos de registro y Unión si es probable que evolucione el diseño de estos tipos</span><span class="sxs-lookup"><span data-stu-id="19be2-274">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="19be2-275">Evite revelar representaciones concretas de objetos.</span><span class="sxs-lookup"><span data-stu-id="19be2-275">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="19be2-276">Por ejemplo, la <xref:System.DateTime> API pública externa del diseño de la biblioteca de .net no revela la representación concreta de los valores.</span><span class="sxs-lookup"><span data-stu-id="19be2-276">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="19be2-277">En tiempo de ejecución, Common Language Runtime conoce la implementación confirmada que se utilizará a lo largo de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="19be2-277">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="19be2-278">Sin embargo, el código compilado no selecciona las dependencias en la representación concreta.</span><span class="sxs-lookup"><span data-stu-id="19be2-278">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="19be2-279">Evitar el uso de la herencia de implementación para la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="19be2-279">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="19be2-280">En F #, rara vez se utiliza la herencia de implementación.</span><span class="sxs-lookup"><span data-stu-id="19be2-280">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="19be2-281">Además, las jerarquías de herencia suelen ser complejas y difíciles de cambiar cuando llegan nuevos requisitos.</span><span class="sxs-lookup"><span data-stu-id="19be2-281">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="19be2-282">La implementación de la herencia todavía existe en F # por compatibilidad y casos raros en los que es la mejor solución para un problema, pero se deben buscar técnicas alternativas en los programas de F # al diseñar el polimorfismo, como la implementación de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="19be2-282">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="19be2-283">Firmas de función y de miembro</span><span class="sxs-lookup"><span data-stu-id="19be2-283">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="19be2-284">Usar tuplas para valores devueltos al devolver un número pequeño de varios valores no relacionados</span><span class="sxs-lookup"><span data-stu-id="19be2-284">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="19be2-285">Este es un buen ejemplo del uso de una tupla en un tipo de valor devuelto:</span><span class="sxs-lookup"><span data-stu-id="19be2-285">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="19be2-286">En el caso de los tipos de valor devueltos que contienen muchos componentes, o en los que los componentes están relacionados con una sola entidad identificable, considere la posibilidad de usar un tipo con nombre en lugar de una tupla.</span><span class="sxs-lookup"><span data-stu-id="19be2-286">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="19be2-287">Se usa `Async<T>` para la programación asincrónica en los límites de la API de F #</span><span class="sxs-lookup"><span data-stu-id="19be2-287">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="19be2-288">Si hay una operación sincrónica correspondiente denominada `Operation` que devuelve un `T` , se debe asignar un nombre a la operación asincrónica `AsyncOperation` si devuelve `Async<T>` o `OperationAsync` si devuelve `Task<T>` .</span><span class="sxs-lookup"><span data-stu-id="19be2-288">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="19be2-289">En el caso de los tipos de .NET que se usan habitualmente y que exponen métodos Begin/end, considere la posibilidad de usar `Async.FromBeginEnd` para escribir métodos de extensión como una fachada para proporcionar el modelo de programación de F # Async a esas API de .net.</span><span class="sxs-lookup"><span data-stu-id="19be2-289">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="19be2-290">Excepciones</span><span class="sxs-lookup"><span data-stu-id="19be2-290">Exceptions</span></span>

<span data-ttu-id="19be2-291">Consulte [Administración de errores](conventions.md#error-management) para obtener información sobre el uso adecuado de excepciones, resultados y opciones.</span><span class="sxs-lookup"><span data-stu-id="19be2-291">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="19be2-292">Miembros de extensión</span><span class="sxs-lookup"><span data-stu-id="19be2-292">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="19be2-293">Aplicar cuidadosamente los miembros de extensión de F # en componentes de F # a-F #</span><span class="sxs-lookup"><span data-stu-id="19be2-293">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="19be2-294">Normalmente, los miembros de extensión de F # solo se deben usar para las operaciones que se encuentran en el cierre de operaciones intrínsecas asociadas a un tipo en la mayoría de los modos de uso.</span><span class="sxs-lookup"><span data-stu-id="19be2-294">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="19be2-295">Un uso común es proporcionar API más idiomático a F # para varios tipos de .NET:</span><span class="sxs-lookup"><span data-stu-id="19be2-295">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="19be2-296">Tipos de Unión</span><span class="sxs-lookup"><span data-stu-id="19be2-296">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="19be2-297">Usar uniones discriminadas en lugar de jerarquías de clases para los datos estructurados por árbol</span><span class="sxs-lookup"><span data-stu-id="19be2-297">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="19be2-298">Las estructuras de tipo árbol se definen de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="19be2-298">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="19be2-299">Esto es complicado con la herencia, pero elegante con uniones discriminadas.</span><span class="sxs-lookup"><span data-stu-id="19be2-299">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="19be2-300">Representar datos similares a los árboles con uniones discriminadas también le permite beneficiarse de la en la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="19be2-300">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="19be2-301">Usar `[<RequireQualifiedAccess>]` en tipos de Unión cuyos nombres de caso no son suficientemente únicos</span><span class="sxs-lookup"><span data-stu-id="19be2-301">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="19be2-302">Puede que se encuentre en un dominio en el que el mismo nombre sea el mejor para cosas diferentes, como casos de Unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="19be2-302">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="19be2-303">Puede usar para eliminar la `[<RequireQualifiedAccess>]` ambigüedad de los nombres de mayúsculas y minúsculas con el fin de evitar que se produzcan errores confusos debido al sombreado dependiente del orden de las `open` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="19be2-303">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="19be2-304">Ocultar las representaciones de las uniones discriminadas para las API compatibles con binario si es probable que evolucione el diseño de estos tipos</span><span class="sxs-lookup"><span data-stu-id="19be2-304">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="19be2-305">Los tipos uniones se basan en formularios de coincidencia de patrones de F # para un modelo de programación conciso.</span><span class="sxs-lookup"><span data-stu-id="19be2-305">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="19be2-306">Como se mencionó anteriormente, debe evitar revelar representaciones de datos concretas si es probable que evolucione el diseño de estos tipos.</span><span class="sxs-lookup"><span data-stu-id="19be2-306">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="19be2-307">Por ejemplo, la representación de una Unión discriminada se puede ocultar mediante una declaración privada o interna, o mediante un archivo de signatura.</span><span class="sxs-lookup"><span data-stu-id="19be2-307">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="19be2-308">Si revela las uniones discriminadas indiscriminadamente, puede que le resulte difícil crear una versión de la biblioteca sin interrumpir el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="19be2-308">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="19be2-309">En su lugar, considere la posibilidad de mostrar uno o varios patrones activos para permitir la coincidencia de patrones con los valores de su tipo.</span><span class="sxs-lookup"><span data-stu-id="19be2-309">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="19be2-310">Los modelos activos proporcionan una forma alternativa de proporcionar a los consumidores de F # la coincidencia de patrones, al mismo tiempo que evitan exponer directamente los tipos de unión de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-310">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="19be2-311">Funciones insertadas y restricciones de miembro</span><span class="sxs-lookup"><span data-stu-id="19be2-311">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="19be2-312">Definir algoritmos numéricos genéricos mediante funciones insertadas con restricciones de miembros implícitas y tipos genéricos resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="19be2-312">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="19be2-313">Las restricciones de miembros aritméticos y las restricciones de comparación de F # son un estándar para la programación en F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-313">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="19be2-314">Por ejemplo, considere el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="19be2-314">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="19be2-315">El tipo de esta función es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="19be2-315">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="19be2-316">Se trata de una función adecuada para una API pública en una biblioteca matemática.</span><span class="sxs-lookup"><span data-stu-id="19be2-316">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="19be2-317">Evite el uso de restricciones de miembro para simular clases de tipos y tipos de patos</span><span class="sxs-lookup"><span data-stu-id="19be2-317">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="19be2-318">Es posible simular "Duck Typing" con las restricciones de miembro de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-318">It is possible to simulate "duck typing" using F# member constraints.</span></span> <span data-ttu-id="19be2-319">Sin embargo, los miembros que hacen uso de esto no deben usarse en general en los diseños de la biblioteca de F # a-F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-319">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="19be2-320">Esto se debe a que los diseños de biblioteca basados en restricciones implícitas no conocidas o no estándar tienden a hacer que el código de usuario sea inflexible y vinculado a un patrón de marco de trabajo determinado.</span><span class="sxs-lookup"><span data-stu-id="19be2-320">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="19be2-321">Además, existe la posibilidad de que el uso intensivo de restricciones de miembros de esta manera pueda producir tiempos de compilación muy largos.</span><span class="sxs-lookup"><span data-stu-id="19be2-321">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="19be2-322">Definiciones de operador</span><span class="sxs-lookup"><span data-stu-id="19be2-322">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="19be2-323">Evite definir operadores simbólicos personalizados</span><span class="sxs-lookup"><span data-stu-id="19be2-323">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="19be2-324">Los operadores personalizados son esenciales en algunas situaciones y son dispositivos de notación muy útiles en un gran número de código de implementación.</span><span class="sxs-lookup"><span data-stu-id="19be2-324">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="19be2-325">En el caso de los nuevos usuarios de una biblioteca, las funciones con nombre suelen ser más fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="19be2-325">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="19be2-326">Además, los operadores simbólicos personalizados pueden ser difíciles de documentar y los usuarios le resultarán más difíciles de buscar ayuda sobre los operadores, debido a las limitaciones existentes en el IDE y los motores de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="19be2-326">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="19be2-327">Como resultado, es mejor publicar su funcionalidad como funciones y miembros con nombre y, además, exponer operadores para esta funcionalidad solo si las ventajas de la notación son más importantes que la documentación y el costo cognitivo de tenerlos.</span><span class="sxs-lookup"><span data-stu-id="19be2-327">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="19be2-328">Unidades de medida</span><span class="sxs-lookup"><span data-stu-id="19be2-328">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="19be2-329">Usar cuidadosamente unidades de medida para la seguridad de tipos agregada en código de F #</span><span class="sxs-lookup"><span data-stu-id="19be2-329">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="19be2-330">La información de escritura adicional para las unidades de medida se borra cuando la ven otros lenguajes de .NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-330">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="19be2-331">Tenga en cuenta que los componentes, las herramientas y la reflexión de .NET verán tipos-sans-units.</span><span class="sxs-lookup"><span data-stu-id="19be2-331">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="19be2-332">Por ejemplo, los consumidores de C# verán `float` en lugar de `float<kg>` .</span><span class="sxs-lookup"><span data-stu-id="19be2-332">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="19be2-333">Abreviaturas de tipo</span><span class="sxs-lookup"><span data-stu-id="19be2-333">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="19be2-334">Usar cuidadosamente las abreviaturas de tipo para simplificar el código de F #</span><span class="sxs-lookup"><span data-stu-id="19be2-334">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="19be2-335">Los componentes, las herramientas y la reflexión de .NET no verán los nombres abreviados de los tipos.</span><span class="sxs-lookup"><span data-stu-id="19be2-335">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="19be2-336">El uso significativo de las abreviaturas de tipo también puede hacer que un dominio parezca más complejo de lo que realmente es, lo que puede confundir a los consumidores.</span><span class="sxs-lookup"><span data-stu-id="19be2-336">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="19be2-337">Evite las abreviaturas de tipo para los tipos públicos cuyos miembros y propiedades deben ser intrínsecamente diferentes a los disponibles en el tipo que se va a abreviar.</span><span class="sxs-lookup"><span data-stu-id="19be2-337">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="19be2-338">En este caso, el tipo que se va a abreviar revela demasiada información sobre la representación del tipo real que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="19be2-338">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="19be2-339">En su lugar, considere la posibilidad de ajustar la abreviatura en un tipo de clase o en una Unión discriminada de un caso (o, cuando el rendimiento sea esencial, considere la posibilidad de usar un tipo de struct para encapsular la abreviatura).</span><span class="sxs-lookup"><span data-stu-id="19be2-339">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="19be2-340">Por ejemplo, es tentador definir un mapa múltiple como un caso especial de un mapa de F #, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19be2-340">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="19be2-341">Sin embargo, las operaciones de notación de puntos lógicas de este tipo no son las mismas que las operaciones en un mapa; por ejemplo, es razonable que la asignación del operador de búsqueda. [Key] devuelve la lista vacía si la clave no está en el diccionario, en lugar de generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="19be2-341">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="19be2-342">Directrices para las bibliotecas para su uso desde otros lenguajes .NET</span><span class="sxs-lookup"><span data-stu-id="19be2-342">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="19be2-343">Al diseñar bibliotecas para su uso desde otros lenguajes .NET, es importante cumplir las directrices de [diseño](../../standard/design-guidelines/index.md)de la biblioteca de .net.</span><span class="sxs-lookup"><span data-stu-id="19be2-343">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="19be2-344">En este documento, estas bibliotecas se etiquetan como bibliotecas de .NET de vainilla, a diferencia de las bibliotecas de F # orientadas a las que usan construcciones de F # sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="19be2-344">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="19be2-345">El diseño de las bibliotecas .NET de vainilla permite proporcionar API conocidas y idiomáticos coherentes con el resto de los .NET Framework al minimizar el uso de construcciones específicas de F # en la API pública.</span><span class="sxs-lookup"><span data-stu-id="19be2-345">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="19be2-346">Las reglas se explican en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="19be2-346">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="19be2-347">Espacio de nombres y diseño de tipos (para bibliotecas para su uso desde otros lenguajes .NET)</span><span class="sxs-lookup"><span data-stu-id="19be2-347">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="19be2-348">Aplicar las convenciones de nomenclatura de .NET a la API pública de los componentes</span><span class="sxs-lookup"><span data-stu-id="19be2-348">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="19be2-349">Preste especial atención al uso de nombres abreviados y a las directrices de capitalización de .NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-349">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="19be2-350">Usar espacios de nombres, tipos y miembros como la estructura organizativa principal de los componentes</span><span class="sxs-lookup"><span data-stu-id="19be2-350">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="19be2-351">Todos los archivos que contienen funcionalidad pública deben comenzar con una `namespace` declaración y las únicas entidades de acceso público de los espacios de nombres deben ser tipos.</span><span class="sxs-lookup"><span data-stu-id="19be2-351">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="19be2-352">No use módulos de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-352">Do not use F# modules.</span></span>

<span data-ttu-id="19be2-353">Use módulos no públicos para almacenar el código de implementación, los tipos de utilidad y las funciones de utilidad.</span><span class="sxs-lookup"><span data-stu-id="19be2-353">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="19be2-354">Los tipos estáticos deben ser preferibles a los módulos, ya que permiten la evolución futura de la API para usar la sobrecarga y otros conceptos de diseño de la API de .NET que no se pueden usar en los módulos de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-354">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="19be2-355">Por ejemplo, en lugar de la siguiente API pública:</span><span class="sxs-lookup"><span data-stu-id="19be2-355">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="19be2-356">En su lugar, considere:</span><span class="sxs-lookup"><span data-stu-id="19be2-356">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="19be2-357">Usar tipos de registro de F # en las API de .NET de vainilla si el diseño de los tipos no evolucionará</span><span class="sxs-lookup"><span data-stu-id="19be2-357">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="19be2-358">Los tipos de registro de F # se compilan en una clase .NET simple.</span><span class="sxs-lookup"><span data-stu-id="19be2-358">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="19be2-359">Son adecuadas para algunos tipos simples y estables en las API.</span><span class="sxs-lookup"><span data-stu-id="19be2-359">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="19be2-360">Considere la posibilidad de usar los `[<NoEquality>]` `[<NoComparison>]` atributos y para suprimir la generación automática de interfaces.</span><span class="sxs-lookup"><span data-stu-id="19be2-360">Consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="19be2-361">Evite también el uso de campos de registro mutables en las API de .NET de vainilla, ya que exponen un campo público.</span><span class="sxs-lookup"><span data-stu-id="19be2-361">Also avoid using mutable record fields in vanilla .NET APIs as these expose a public field.</span></span> <span data-ttu-id="19be2-362">Considere siempre si una clase proporcionaría una opción más flexible para la evolución futura de la API.</span><span class="sxs-lookup"><span data-stu-id="19be2-362">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="19be2-363">Por ejemplo, el siguiente código de F # expone la API pública a un consumidor de C#:</span><span class="sxs-lookup"><span data-stu-id="19be2-363">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="19be2-364">F#:</span><span class="sxs-lookup"><span data-stu-id="19be2-364">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

<span data-ttu-id="19be2-365">C#:</span><span class="sxs-lookup"><span data-stu-id="19be2-365">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="19be2-366">Ocultar la representación de tipos de unión de F # en las API de .NET de vainilla</span><span class="sxs-lookup"><span data-stu-id="19be2-366">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="19be2-367">Los tipos de unión de f # no se usan habitualmente en los límites de los componentes, ni siquiera para la codificación de F # a F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-367">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="19be2-368">Son un dispositivo de implementación excelente cuando se usan internamente en componentes y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="19be2-368">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="19be2-369">Al diseñar una API de .NET de vainilla, considere la posibilidad de ocultar la representación de un tipo de Unión mediante una declaración privada o un archivo de signatura.</span><span class="sxs-lookup"><span data-stu-id="19be2-369">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="19be2-370">También puede aumentar los tipos que usan internamente una representación de unión con los miembros para proporcionar el deseado. API orientada a redes.</span><span class="sxs-lookup"><span data-stu-id="19be2-370">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="19be2-371">Diseñar GUI y otros componentes mediante los modelos de diseño del marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="19be2-371">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="19be2-372">Hay muchos marcos de trabajo diferentes disponibles en .NET, como WinForms, WPF y ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-372">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="19be2-373">Las convenciones de nomenclatura y diseño de cada una deben usarse si se diseñan componentes para su uso en estos marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="19be2-373">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="19be2-374">Por ejemplo, para la programación de WPF, adopte patrones de diseño de WPF para las clases que está diseñando.</span><span class="sxs-lookup"><span data-stu-id="19be2-374">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="19be2-375">En el caso de los modelos de programación de la interfaz de usuario, utilice patrones de diseño como eventos y colecciones basadas en notificaciones, como las que se encuentran en <xref:System.Collections.ObjectModel> .</span><span class="sxs-lookup"><span data-stu-id="19be2-375">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="19be2-376">Diseño de objetos y miembros (para bibliotecas para su uso desde otros lenguajes .NET)</span><span class="sxs-lookup"><span data-stu-id="19be2-376">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="19be2-377">Usar el atributo CLIEvent para exponer eventos de .NET</span><span class="sxs-lookup"><span data-stu-id="19be2-377">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="19be2-378">Construya un `DelegateEvent` con un tipo de delegado .net específico que toma un objeto y `EventArgs` (en lugar de un `Event` , que simplemente usa el `FSharpHandler` tipo de forma predeterminada) para que los eventos se publiquen de la manera más familiar que otros lenguajes .net.</span><span class="sxs-lookup"><span data-stu-id="19be2-378">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a><span data-ttu-id="19be2-379">Exponer operaciones asincrónicas como métodos que devuelven tareas de .NET</span><span class="sxs-lookup"><span data-stu-id="19be2-379">Expose asynchronous operations as methods that return .NET tasks</span></span>

<span data-ttu-id="19be2-380">Las tareas se usan en .NET para representar los cálculos asincrónicos activos.</span><span class="sxs-lookup"><span data-stu-id="19be2-380">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="19be2-381">En general, las tareas son menos compuestas que los objetos de F # `Async<T>` , ya que representan las tareas que ya se están ejecutando y no se pueden componer juntas de forma que realicen la composición paralela, o que ocultan la propagación de señales de cancelación y otros parámetros contextuales.</span><span class="sxs-lookup"><span data-stu-id="19be2-381">Tasks are in general less compositional than F# `Async<T>` objects, since they represent "already executing" tasks and can't be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="19be2-382">Sin embargo, a pesar de ello, los métodos que devuelven tareas son la representación estándar de la programación asincrónica en .NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-382">However, despite this, methods that return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="19be2-383">Normalmente, también querrá aceptar un token de cancelación explícito:</span><span class="sxs-lookup"><span data-stu-id="19be2-383">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="19be2-384">Usar tipos de delegado de .NET en lugar de tipos de función de F #</span><span class="sxs-lookup"><span data-stu-id="19be2-384">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="19be2-385">Aquí "tipos de funciones de F #" significan tipos de "flecha" como `int -> int` .</span><span class="sxs-lookup"><span data-stu-id="19be2-385">Here "F# function types" mean "arrow" types like `int -> int`.</span></span>

<span data-ttu-id="19be2-386">En lugar de esto:</span><span class="sxs-lookup"><span data-stu-id="19be2-386">Instead of this:</span></span>

```fsharp
member this.Transform(f: int->int) =
    ...
```

<span data-ttu-id="19be2-387">Haga esto:</span><span class="sxs-lookup"><span data-stu-id="19be2-387">Do this:</span></span>

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

<span data-ttu-id="19be2-388">El tipo de función de F # aparece como `class FSharpFunc<T,U>` en otros lenguajes .net y es menos adecuado para las características del lenguaje y las herramientas que comprenden los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="19be2-388">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understands delegate types.</span></span> <span data-ttu-id="19be2-389">Al crear un método de orden superior que tenga como destino .NET Framework 3,5 o superior, `System.Func` los `System.Action` delegados y son las API adecuadas para publicar y permitir a los desarrolladores de .net usar estas API de manera insuficiente.</span><span class="sxs-lookup"><span data-stu-id="19be2-389">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="19be2-390">(Cuando el destino es .NET Framework 2,0, los tipos de delegado definidos por el sistema son más limitados; considere la posibilidad de usar tipos de delegado predefinidos como `System.Converter<T,U>` o definir un tipo de delegado específico).</span><span class="sxs-lookup"><span data-stu-id="19be2-390">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="19be2-391">En el lado de volteo, los delegados de .NET no son naturales para las bibliotecas orientadas a F # (vea la siguiente sección sobre bibliotecas orientadas a F #).</span><span class="sxs-lookup"><span data-stu-id="19be2-391">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="19be2-392">Como resultado, una estrategia de implementación común al desarrollar métodos de orden superior para las bibliotecas de .NET de vainilla es crear toda la implementación con los tipos de función de F # y, a continuación, crear la API pública mediante delegados como una fachada fina sobre la implementación real de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-392">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="19be2-393">Use el patrón TryGetValue en lugar de devolver valores de opción de F # y preferir la sobrecarga del método para tomar los valores de las opciones de F # como argumentos.</span><span class="sxs-lookup"><span data-stu-id="19be2-393">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="19be2-394">Los patrones comunes de uso para el tipo de opción de F # en las API se implementan mejor en las API de .NET de vainilla mediante técnicas de diseño estándar de .NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-394">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="19be2-395">En lugar de devolver un valor de opción de F #, considere la posibilidad de usar el tipo de valor devuelto bool junto con un parámetro out como en el patrón "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="19be2-395">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="19be2-396">Y en lugar de tomar los valores de las opciones de F # como parámetros, considere la posibilidad de usar la sobrecarga de métodos o argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="19be2-396">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="19be2-397">Usar los tipos de interfaz de colección de .NET IEnumerable \< T \> y la \< clave IDictionary, el valor \> para los parámetros y los valores devueltos</span><span class="sxs-lookup"><span data-stu-id="19be2-397">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="19be2-398">Evite el uso de tipos de colección concretos como matrices de .NET `T[]` , tipos de F # y `list<T>` `Map<Key,Value>` `Set<T>` , y tipos de colección concretos de .net como `Dictionary<Key,Value>` .</span><span class="sxs-lookup"><span data-stu-id="19be2-398">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="19be2-399">Las instrucciones de diseño de la biblioteca de .NET tienen buenos consejos sobre Cuándo usar varios tipos de colección como `IEnumerable<T>` .</span><span class="sxs-lookup"><span data-stu-id="19be2-399">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="19be2-400">El uso de matrices ( `T[]` ) es aceptable en algunas circunstancias, por motivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="19be2-400">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="19be2-401">Tenga en cuenta especialmente que `seq<T>` es solo el alias de F # para `IEnumerable<T>` y, por lo tanto, SEQ suele ser un tipo adecuado para una API de .net de vainilla.</span><span class="sxs-lookup"><span data-stu-id="19be2-401">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="19be2-402">En lugar de listas de F #:</span><span class="sxs-lookup"><span data-stu-id="19be2-402">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names: string list) =
    ...
```

<span data-ttu-id="19be2-403">Usar secuencias de F #:</span><span class="sxs-lookup"><span data-stu-id="19be2-403">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="19be2-404">Use el tipo de unidad como el único tipo de entrada de un método para definir un método de argumento cero, o como el único tipo de valor devuelto para definir un método que devuelve void.</span><span class="sxs-lookup"><span data-stu-id="19be2-404">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="19be2-405">Evite otros usos del tipo de unidad.</span><span class="sxs-lookup"><span data-stu-id="19be2-405">Avoid other uses of the unit type.</span></span> <span data-ttu-id="19be2-406">Estos son buenos:</span><span class="sxs-lookup"><span data-stu-id="19be2-406">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

<span data-ttu-id="19be2-407">Esto no es válido:</span><span class="sxs-lookup"><span data-stu-id="19be2-407">This is bad:</span></span>

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="19be2-408">Comprobar si hay valores NULL en los límites de la API de .NET de vainilla</span><span class="sxs-lookup"><span data-stu-id="19be2-408">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="19be2-409">El código de implementación de F # tiende a tener menos valores NULL, debido a las restricciones y patrones de diseño inmutables sobre el uso de literales null para los tipos de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-409">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="19be2-410">Otros lenguajes .NET suelen usar NULL como valor con mucha más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="19be2-410">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="19be2-411">Por este motivo, el código de F # que expone una API de .NET de vainilla debe comprobar los parámetros null en el límite de la API y evitar que estos valores fluyan más en el código de implementación de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-411">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="19be2-412">`isNull`Se puede usar la función o coincidencia de patrones en el `null` patrón.</span><span class="sxs-lookup"><span data-stu-id="19be2-412">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="19be2-413">Evite el uso de tuplas como valores devueltos</span><span class="sxs-lookup"><span data-stu-id="19be2-413">Avoid using tuples as return values</span></span>

<span data-ttu-id="19be2-414">En su lugar, se prefiere devolver un tipo con nombre que contenga los datos agregados o usar parámetros out para devolver varios valores.</span><span class="sxs-lookup"><span data-stu-id="19be2-414">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="19be2-415">Aunque las tuplas de estructuras y de struct existen en .NET (incluida la compatibilidad con el lenguaje C# para las tuplas de struct), a menudo no proporcionarán la API ideal y la esperada para los desarrolladores de .NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-415">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="19be2-416">Evitar el uso de currificación de parámetros</span><span class="sxs-lookup"><span data-stu-id="19be2-416">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="19be2-417">En su lugar, use convenciones de llamada de .NET `Method(arg1,arg2,…,argN)` .</span><span class="sxs-lookup"><span data-stu-id="19be2-417">Instead, use .NET calling conventions `Method(arg1,arg2,…,argN)`.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="19be2-418">Sugerencia: Si está diseñando bibliotecas para su uso desde cualquier lenguaje .NET, no habrá ningún sustituto para realizar realmente alguna programación experimental de C# y Visual Basic para asegurarse de que las bibliotecas "se sienten bien" desde estos lenguajes.</span><span class="sxs-lookup"><span data-stu-id="19be2-418">Tip: If you're designing libraries for use from any .NET language, then there's no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="19be2-419">También puede usar herramientas como .NET reflector y el Examinador de objetos de Visual Studio para asegurarse de que las bibliotecas y su documentación aparecen como se espera para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="19be2-419">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="19be2-420">Apéndice</span><span class="sxs-lookup"><span data-stu-id="19be2-420">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="19be2-421">Ejemplo de un extremo a otro del diseño de código de F # para su uso por parte de otros lenguajes .NET</span><span class="sxs-lookup"><span data-stu-id="19be2-421">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="19be2-422">Considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="19be2-422">Consider the following class:</span></span>

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

<span data-ttu-id="19be2-423">El tipo de F # deducido de esta clase es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="19be2-423">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="19be2-424">Echemos un vistazo a cómo se muestra este tipo de F # a un programador con otro lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="19be2-424">Let's take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="19be2-425">Por ejemplo, la "firma" de C# aproximada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="19be2-425">For example, the approximate C# "signature" is as follows:</span></span>

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

<span data-ttu-id="19be2-426">Hay algunos aspectos importantes que se deben tener en cuenta sobre cómo F # representa las construcciones aquí.</span><span class="sxs-lookup"><span data-stu-id="19be2-426">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="19be2-427">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="19be2-427">For example:</span></span>

* <span data-ttu-id="19be2-428">Se han conservado los metadatos, como los nombres de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="19be2-428">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="19be2-429">Los métodos de F # que toman dos argumentos se convierten en métodos de C# que toman dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="19be2-429">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="19be2-430">Las funciones y las listas se convierten en referencias a los tipos correspondientes de la biblioteca de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-430">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="19be2-431">En el código siguiente se muestra cómo ajustar este código para tener en cuenta estos aspectos.</span><span class="sxs-lookup"><span data-stu-id="19be2-431">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="19be2-432">El tipo de F # deducido del código es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="19be2-432">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="19be2-433">La firma de C# es ahora como sigue:</span><span class="sxs-lookup"><span data-stu-id="19be2-433">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="19be2-434">Las correcciones realizadas para preparar este tipo para su uso como parte de una biblioteca .NET de vainilla son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="19be2-434">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="19be2-435">Se han ajustado varios nombres: `Point1` , `n` , y se han convertido en `l` `f` `RadialPoint` , `count` , `factor` y `transform` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="19be2-435">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="19be2-436">Se usa un tipo de valor devuelto de en `seq<RadialPoint>` lugar de `RadialPoint list` cambiar una construcción de lista mediante `[ ... ]` a una construcción de secuencia mediante `IEnumerable<RadialPoint>` .</span><span class="sxs-lookup"><span data-stu-id="19be2-436">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="19be2-437">Se usa el tipo de delegado de .NET `System.Func` en lugar de un tipo de función de F #.</span><span class="sxs-lookup"><span data-stu-id="19be2-437">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="19be2-438">Esto hace que sea mucho más agradable usar en el código de C#.</span><span class="sxs-lookup"><span data-stu-id="19be2-438">This makes it far nicer to consume in C# code.</span></span>
