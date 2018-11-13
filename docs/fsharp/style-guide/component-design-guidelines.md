---
title: Instrucciones de diseño del componente de F#
description: Obtenga información sobre las directrices para escribir componentes de F# pensados para su uso por otros llamadores.
ms.date: 05/14/2018
ms.openlocfilehash: 446cba0f810af9517b655ef5741ddf7a919676d5
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43488292"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="23ba3-103">Instrucciones de diseño del componente de F#</span><span class="sxs-lookup"><span data-stu-id="23ba3-103">F# component design guidelines</span></span>

<span data-ttu-id="23ba3-104">Este documento es un conjunto de directrices de diseño del componente de F# de programación, en función de la F# componente instrucciones de diseño, v14, Microsoft Research, y [otra versión](https://fsharp.org/specs/component-design-guidelines/) originalmente seleccionada y mantenido por F# Software Foundation.</span><span class="sxs-lookup"><span data-stu-id="23ba3-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="23ba3-105">Este documento se da por supuesto que está familiarizado con la programación en F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="23ba3-106">Muchas gracias a la Comunidad de F# por sus aportaciones y comentarios útiles en varias versiones de esta guía.</span><span class="sxs-lookup"><span data-stu-id="23ba3-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="23ba3-107">Información general</span><span class="sxs-lookup"><span data-stu-id="23ba3-107">Overview</span></span>

<span data-ttu-id="23ba3-108">Este documento se examina algunos de los problemas relacionados con la codificación y diseño del componente de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="23ba3-109">Un componente puede significar cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="23ba3-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="23ba3-110">Una capa en el proyecto de F# que tiene los consumidores externos dentro de ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="23ba3-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="23ba3-111">Una biblioteca pensada para su uso por código de F# a través de límites de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23ba3-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="23ba3-112">Una biblioteca diseñada para su uso en cualquier lenguaje .NET entre límites de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23ba3-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="23ba3-113">Una biblioteca diseñada para su distribución a través de un repositorio de paquetes, tales como [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="23ba3-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="23ba3-114">Las técnicas descritas en este artículo siguen el [cinco principios del buen código de F#](index.md#five-principles-of-good-f-code)y, por tanto, usar ambos funcional y objeto de programación según corresponda.</span><span class="sxs-lookup"><span data-stu-id="23ba3-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="23ba3-115">Independientemente de la metodología, el Diseñador de componentes y la biblioteca enfrenta una serie de problemas prácticas y prosaicos al tratar de diseñar una API que se puede usar más fácilmente los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="23ba3-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="23ba3-116">Una aplicación muy consciente de la [instrucciones de diseño de bibliotecas de .NET](../../standard/design-guidelines/index.md) encaminarse hacia la creación de un conjunto coherente de API que están agradables para consumir.</span><span class="sxs-lookup"><span data-stu-id="23ba3-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="23ba3-117">Instrucciones generales</span><span class="sxs-lookup"><span data-stu-id="23ba3-117">General guidelines</span></span>

<span data-ttu-id="23ba3-118">Hay algunas instrucciones universales que se aplican a las bibliotecas F#, independientemente de la audiencia objetivo de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="23ba3-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="23ba3-119">Obtenga información sobre las instrucciones de diseño de la biblioteca de .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="23ba3-120">Independientemente del tipo de F# de codificación está realizando, es útil tener conocimientos prácticos de la [instrucciones de diseño de bibliotecas de .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="23ba3-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="23ba3-121">La mayoría otros F# y los programadores de .NET se está familiarizado con estas directrices y esperar que el código de .NET para ajustarse a ellos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="23ba3-122">Las instrucciones de diseño de la biblioteca de .NET proporcionan información general sobre la nomenclatura, diseño de clases y las interfaces, diseño de miembros (propiedades, métodos, eventos, etc.) y mucho más y son útil primer punto de referencia para una variedad de instrucciones de diseño.</span><span class="sxs-lookup"><span data-stu-id="23ba3-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="23ba3-123">Agregar comentarios de documentación XML en el código</span><span class="sxs-lookup"><span data-stu-id="23ba3-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="23ba3-124">Documentación XML en las API públicas Asegúrese de que los usuarios pueden obtener gran Intellisense y Quickinfo al utilizar estos tipos y miembros y habilitar documentación para crear archivos de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="23ba3-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="23ba3-125">Consulte la [documentación XML](../language-reference/xml-documentation.md) sobre diversas etiquetas xml que se pueden usar para el marcado adicional dentro de los comentarios de xmldoc.</span><span class="sxs-lookup"><span data-stu-id="23ba3-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="23ba3-126">Puede usar los comentarios XML de forma abreviada (`/// comment`), o los comentarios XML estándar (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="23ba3-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="23ba3-127">Considere el uso de archivos explícita signatura (.fsi) para la biblioteca estable y las API de componentes</span><span class="sxs-lookup"><span data-stu-id="23ba3-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="23ba3-128">Uso de archivos de firmas explícita en una biblioteca de F# proporciona un breve resumen de API pública, que ayuda a garantizar que se conoce la superficie pública completa de la biblioteca, así como proporciona una separación limpia entre documentación pública e internos detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="23ba3-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="23ba3-129">Tenga en cuenta que los archivos de firma agregan fricción al cambio de la API pública, al requerir que los cambios que se realizan en los archivos de la implementación y la firma.</span><span class="sxs-lookup"><span data-stu-id="23ba3-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="23ba3-130">Como resultado, los archivos de firma normalmente solo se deben agregar cuando una API ha consolidado a convertirse en y ya no se espera que cambie significativamente.</span><span class="sxs-lookup"><span data-stu-id="23ba3-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="23ba3-131">Siga siempre las prácticas recomendadas para el uso de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="23ba3-132">Siga [prácticas recomendadas para el uso de cadenas en .NET](../../standard/base-types/best-practices-strings.md) orientación.</span><span class="sxs-lookup"><span data-stu-id="23ba3-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="23ba3-133">En concreto, siempre explícitamente *intención cultural* en la conversión y la comparación de cadenas (si procede).</span><span class="sxs-lookup"><span data-stu-id="23ba3-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="23ba3-134">Directrices para F#-orientado a las bibliotecas</span><span class="sxs-lookup"><span data-stu-id="23ba3-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="23ba3-135">En esta sección se presenta recomendaciones para el desarrollo de F# pública-orientado a las bibliotecas; es decir, las bibliotecas de exponer las API públicas que vayan a ser consumidos por los desarrolladores de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="23ba3-136">Hay una variedad de recomendaciones de diseño de la biblioteca aplicables específicamente a F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="23ba3-137">En ausencia de las recomendaciones específicas que siguen, las instrucciones de diseño de la biblioteca de .NET son las instrucciones de reserva.</span><span class="sxs-lookup"><span data-stu-id="23ba3-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="23ba3-138">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="23ba3-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="23ba3-139">Usar las convenciones de mayúsculas y minúsculas y nomenclatura de .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="23ba3-140">La siguiente tabla sigue las convenciones de mayúsculas y minúsculas y nomenclatura. NET.</span><span class="sxs-lookup"><span data-stu-id="23ba3-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="23ba3-141">Existen adiciones pequeño para incluir también las construcciones de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="23ba3-142">Construcción</span><span class="sxs-lookup"><span data-stu-id="23ba3-142">Construct</span></span> | <span data-ttu-id="23ba3-143">Caso</span><span class="sxs-lookup"><span data-stu-id="23ba3-143">Case</span></span> | <span data-ttu-id="23ba3-144">Parte</span><span class="sxs-lookup"><span data-stu-id="23ba3-144">Part</span></span> | <span data-ttu-id="23ba3-145">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="23ba3-145">Examples</span></span> | <span data-ttu-id="23ba3-146">Notas</span><span class="sxs-lookup"><span data-stu-id="23ba3-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="23ba3-147">Tipos concretos</span><span class="sxs-lookup"><span data-stu-id="23ba3-147">Concrete types</span></span> | <span data-ttu-id="23ba3-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-148">PascalCase</span></span> | <span data-ttu-id="23ba3-149">Sustantivo o adjetivo</span><span class="sxs-lookup"><span data-stu-id="23ba3-149">Noun/ adjective</span></span> | <span data-ttu-id="23ba3-150">Lista, Double, complejo</span><span class="sxs-lookup"><span data-stu-id="23ba3-150">List, Double, Complex</span></span> | <span data-ttu-id="23ba3-151">Tipos concretos son clases, structs, enumeraciones, delegados, registros y uniones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="23ba3-152">Aunque los nombres de tipo son tradicionalmente en minúsculas en OCaml, F# ha adoptado el esquema de nomenclatura .NET para los tipos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="23ba3-153">DLL</span><span class="sxs-lookup"><span data-stu-id="23ba3-153">DLLs</span></span>           | <span data-ttu-id="23ba3-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-154">PascalCase</span></span> |                 | <span data-ttu-id="23ba3-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="23ba3-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="23ba3-156">Etiquetas de unión</span><span class="sxs-lookup"><span data-stu-id="23ba3-156">Union tags</span></span>     | <span data-ttu-id="23ba3-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-157">PascalCase</span></span> | <span data-ttu-id="23ba3-158">Sustantivo</span><span class="sxs-lookup"><span data-stu-id="23ba3-158">Noun</span></span> | <span data-ttu-id="23ba3-159">Algunos, agregar, correcto</span><span class="sxs-lookup"><span data-stu-id="23ba3-159">Some, Add, Success</span></span> | <span data-ttu-id="23ba3-160">No use un prefijo en las API públicas.</span><span class="sxs-lookup"><span data-stu-id="23ba3-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="23ba3-161">Utilizar opcionalmente un prefijo cuando interno, como ''' Escriba equipos = TAlpha</span><span class="sxs-lookup"><span data-stu-id="23ba3-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="23ba3-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="23ba3-162">TBeta</span></span> | <span data-ttu-id="23ba3-163">TDelta.'' '</span><span class="sxs-lookup"><span data-stu-id="23ba3-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="23ba3-164">evento</span><span class="sxs-lookup"><span data-stu-id="23ba3-164">Event</span></span>          | <span data-ttu-id="23ba3-165">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-165">PascalCase</span></span> | <span data-ttu-id="23ba3-166">Verbo</span><span class="sxs-lookup"><span data-stu-id="23ba3-166">Verb</span></span> | <span data-ttu-id="23ba3-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="23ba3-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="23ba3-168">Excepciones</span><span class="sxs-lookup"><span data-stu-id="23ba3-168">Exceptions</span></span>     | <span data-ttu-id="23ba3-169">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-169">PascalCase</span></span> |      | <span data-ttu-id="23ba3-170">WebException</span><span class="sxs-lookup"><span data-stu-id="23ba3-170">WebException</span></span> | <span data-ttu-id="23ba3-171">Nombre debe terminar con "Exception".</span><span class="sxs-lookup"><span data-stu-id="23ba3-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="23ba3-172">Campo</span><span class="sxs-lookup"><span data-stu-id="23ba3-172">Field</span></span>          | <span data-ttu-id="23ba3-173">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-173">PascalCase</span></span> | <span data-ttu-id="23ba3-174">Sustantivo</span><span class="sxs-lookup"><span data-stu-id="23ba3-174">Noun</span></span> | <span data-ttu-id="23ba3-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="23ba3-175">CurrentName</span></span>  | |
| <span data-ttu-id="23ba3-176">Tipos de interfaz</span><span class="sxs-lookup"><span data-stu-id="23ba3-176">Interface types</span></span> |  <span data-ttu-id="23ba3-177">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-177">PascalCase</span></span> | <span data-ttu-id="23ba3-178">Sustantivo o adjetivo</span><span class="sxs-lookup"><span data-stu-id="23ba3-178">Noun/ adjective</span></span> | <span data-ttu-id="23ba3-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="23ba3-179">IDisposable</span></span> | <span data-ttu-id="23ba3-180">Nombre debe comenzar por "I".</span><span class="sxs-lookup"><span data-stu-id="23ba3-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="23ba3-181">Método</span><span class="sxs-lookup"><span data-stu-id="23ba3-181">Method</span></span> |  <span data-ttu-id="23ba3-182">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-182">PascalCase</span></span> |  <span data-ttu-id="23ba3-183">Verbo</span><span class="sxs-lookup"><span data-stu-id="23ba3-183">Verb</span></span> | <span data-ttu-id="23ba3-184">ToString</span><span class="sxs-lookup"><span data-stu-id="23ba3-184">ToString</span></span> | |
| <span data-ttu-id="23ba3-185">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="23ba3-185">Namespace</span></span> | <span data-ttu-id="23ba3-186">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-186">PascalCase</span></span> | | <span data-ttu-id="23ba3-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="23ba3-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="23ba3-188">Generalmente se utiliza `<Organization>.<Technology>[.<Subnamespace>]`, drop aunque la organización si la tecnología es independiente de la organización.</span><span class="sxs-lookup"><span data-stu-id="23ba3-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="23ba3-189">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23ba3-189">Parameters</span></span> | <span data-ttu-id="23ba3-190">camelCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-190">camelCase</span></span> | <span data-ttu-id="23ba3-191">Sustantivo</span><span class="sxs-lookup"><span data-stu-id="23ba3-191">Noun</span></span> |  <span data-ttu-id="23ba3-192">typeName, transformación, intervalo</span><span class="sxs-lookup"><span data-stu-id="23ba3-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="23ba3-193">permitir que los valores (internos)</span><span class="sxs-lookup"><span data-stu-id="23ba3-193">let values (internal)</span></span> | <span data-ttu-id="23ba3-194">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-194">camelCase or PascalCase</span></span> | <span data-ttu-id="23ba3-195">Sustantivo o verbo</span><span class="sxs-lookup"><span data-stu-id="23ba3-195">Noun/ verb</span></span> |  <span data-ttu-id="23ba3-196">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="23ba3-196">getValue, myTable</span></span> |
| <span data-ttu-id="23ba3-197">permitir que los valores (externo)</span><span class="sxs-lookup"><span data-stu-id="23ba3-197">let values (external)</span></span> | <span data-ttu-id="23ba3-198">camelCase o PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-198">camelCase or PascalCase</span></span> | <span data-ttu-id="23ba3-199">Verbo y sustantivo</span><span class="sxs-lookup"><span data-stu-id="23ba3-199">Noun/verb</span></span>  | <span data-ttu-id="23ba3-200">List.Map, Dates.Today</span><span class="sxs-lookup"><span data-stu-id="23ba3-200">List.map, Dates.Today</span></span> | <span data-ttu-id="23ba3-201">a menudo son públicos enlazado a Let valores al seguir los patrones de diseño funcionales tradicional.</span><span class="sxs-lookup"><span data-stu-id="23ba3-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="23ba3-202">Sin embargo, normalmente usar PascalCase cuando el identificador puede usarse desde otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="23ba3-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="23ba3-203">Property</span><span class="sxs-lookup"><span data-stu-id="23ba3-203">Property</span></span>  | <span data-ttu-id="23ba3-204">PascalCase</span><span class="sxs-lookup"><span data-stu-id="23ba3-204">PascalCase</span></span>  | <span data-ttu-id="23ba3-205">Sustantivo o adjetivo</span><span class="sxs-lookup"><span data-stu-id="23ba3-205">Noun/ adjective</span></span>  | <span data-ttu-id="23ba3-206">IsEndOfFile, color de fondo</span><span class="sxs-lookup"><span data-stu-id="23ba3-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="23ba3-207">Las propiedades booleanas generalmente uso es y puede y debe ser afirmativa, como en IsEndOfFile, no IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="23ba3-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="23ba3-208">Evitar las abreviaturas</span><span class="sxs-lookup"><span data-stu-id="23ba3-208">Avoid abbreviations</span></span>

<span data-ttu-id="23ba3-209">Las instrucciones de .NET desaconseja el uso de abreviaturas de (por ejemplo, "usar `OnButtonClick` lugar `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="23ba3-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="23ba3-210">Abreviaturas comunes, como `Async` para "Asynchronous", se tolera.</span><span class="sxs-lookup"><span data-stu-id="23ba3-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="23ba3-211">A veces se pasa por alto esta directriz de programación funcional; Por ejemplo, `List.iter` usa una abreviatura para "recorrer en iteración".</span><span class="sxs-lookup"><span data-stu-id="23ba3-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="23ba3-212">Por este motivo, con abreviaturas tiende a tolerar un mayor grado de F#-a-programación en F#, pero aún por lo general debe evitarse en el diseño del componente público.</span><span class="sxs-lookup"><span data-stu-id="23ba3-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="23ba3-213">Evitar las mayúsculas y minúsculas de las colisiones de nombres</span><span class="sxs-lookup"><span data-stu-id="23ba3-213">Avoid casing name collisions</span></span>

<span data-ttu-id="23ba3-214">Las instrucciones de .NET dicen que las mayúsculas y minúsculas por sí solo no pueden usarse para eliminar la ambigüedad de las colisiones de nombres, ya que algunos idiomas de cliente (por ejemplo, Visual Basic) distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="23ba3-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="23ba3-215">Utilizar acrónimos cuando sea apropiado</span><span class="sxs-lookup"><span data-stu-id="23ba3-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="23ba3-216">Acrónimos como XML no son abreviaturas y se usan ampliamente en las bibliotecas de .NET de forma sin mayúsculas (Xml).</span><span class="sxs-lookup"><span data-stu-id="23ba3-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="23ba3-217">Solo deben usarse acrónimos conocidos y ampliamente reconocidos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="23ba3-218">Uso PascalCase para los nombres de parámetro genérico</span><span class="sxs-lookup"><span data-stu-id="23ba3-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="23ba3-219">Usar PascalCase para nombres de parámetro genérico en las API públicas, incluido para F#-orientado a las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="23ba3-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="23ba3-220">En concreto, use nombres como `T`, `U`, `T1`, `T2` para los parámetros genéricos arbitrarios y nombres específicos tienen sentido, a continuación, para F#-accesibles desde bibliotecas usen nombres como `Key`, `Value`, `Arg`(pero no por ejemplo, `TKey`).</span><span class="sxs-lookup"><span data-stu-id="23ba3-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="23ba3-221">Usar PascalCase o camelCase para funciones públicas y valores en los módulos de F#</span><span class="sxs-lookup"><span data-stu-id="23ba3-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="23ba3-222">camelCase se utiliza para funciones públicas que están diseñadas para usarse incompletos (por ejemplo, `invalidArg`) y para las funciones de colección estándar de"" (por ejemplo, List.map).</span><span class="sxs-lookup"><span data-stu-id="23ba3-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="23ba3-223">En ambos casos, los nombres de función actúan como palabras clave en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="23ba3-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="23ba3-224">Diseño de objeto, tipo y módulo</span><span class="sxs-lookup"><span data-stu-id="23ba3-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="23ba3-225">Usar módulos o espacios de nombres para contener los tipos y módulos</span><span class="sxs-lookup"><span data-stu-id="23ba3-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="23ba3-226">Cada archivo de F# en un componente debe comenzar con una declaración de espacio de nombres o una declaración de módulo.</span><span class="sxs-lookup"><span data-stu-id="23ba3-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="23ba3-227">o</span><span class="sxs-lookup"><span data-stu-id="23ba3-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="23ba3-228">Las diferencias entre el uso de módulos y espacios de nombres para organizar el código en el nivel superior son como sigue:</span><span class="sxs-lookup"><span data-stu-id="23ba3-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="23ba3-229">Los espacios de nombres pueden abarcar varios archivos</span><span class="sxs-lookup"><span data-stu-id="23ba3-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="23ba3-230">Los espacios de nombres no pueden contener funciones de F# a menos que estén dentro de un módulo interno</span><span class="sxs-lookup"><span data-stu-id="23ba3-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="23ba3-231">El código de cualquier módulo determinado debe estar dentro de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="23ba3-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="23ba3-232">Módulos de nivel superior pueden contener funciones de F# sin necesidad de un módulo interno</span><span class="sxs-lookup"><span data-stu-id="23ba3-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="23ba3-233">La elección entre un espacio de nombres de nivel superior o un módulo afecta a la forma compilada del código y, por tanto, afectará a la vista de otros lenguajes .NET su API, finalmente, se debe consumir fuera del código de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="23ba3-234">Usar métodos y propiedades para las operaciones intrínsecas a tipos de objeto</span><span class="sxs-lookup"><span data-stu-id="23ba3-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="23ba3-235">Cuando se trabaja con objetos, es mejor asegurarse de que pueda consumir funcionalidad se implementa como métodos y propiedades de dicho tipo.</span><span class="sxs-lookup"><span data-stu-id="23ba3-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="23ba3-236">La mayor parte de la funcionalidad para un miembro determinado necesita no necesariamente se implementarán en ese miembro, pero debe ser el fragmento consumible de esa funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="23ba3-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="23ba3-237">Usar las clases para encapsular el estado mutable</span><span class="sxs-lookup"><span data-stu-id="23ba3-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="23ba3-238">En F#, esto solo debe hacerse donde que no está encapsulado ya estado por otra construcción del lenguaje, como una clausura, la expresión de secuencia o el cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="23ba3-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="23ba3-239">Usar interfaces para agrupar las operaciones relacionadas con</span><span class="sxs-lookup"><span data-stu-id="23ba3-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="23ba3-240">Usar tipos de interfaz para representar un conjunto de operaciones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="23ba3-241">Esto es preferible a otras opciones, como las tuplas de funciones o los registros de funciones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="23ba3-242">En el lugar para:</span><span class="sxs-lookup"><span data-stu-id="23ba3-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="23ba3-243">Las interfaces son conceptos de primera clase en. NET, que puede usar para lograr lo Functors normalmente le aportara.</span><span class="sxs-lookup"><span data-stu-id="23ba3-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="23ba3-244">Además, puede utilizarse para codificar tipos existenciales en el programa, que no puede ser de los registros de funciones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="23ba3-245">Usar un módulo para las funciones del grupo que actúan en colecciones</span><span class="sxs-lookup"><span data-stu-id="23ba3-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="23ba3-246">Al definir un tipo de colección, considere la posibilidad de proporcionar un conjunto estándar de operaciones como `CollectionType.map` y `CollectionType.iter`) para los nuevos tipos de colección.</span><span class="sxs-lookup"><span data-stu-id="23ba3-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="23ba3-247">Si incluye un módulo de este tipo, siga las convenciones de nomenclatura estándares para las funciones que se encuentra en FSharp.Core.</span><span class="sxs-lookup"><span data-stu-id="23ba3-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="23ba3-248">Usar un módulo para las funciones del grupo para funciones comunes canónicas, especialmente en matemáticas y las bibliotecas DSL</span><span class="sxs-lookup"><span data-stu-id="23ba3-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="23ba3-249">Por ejemplo, `Microsoft.FSharp.Core.Operators` es una colección de funciones de nivel superior abierta automáticamente (como `abs` y `sin`) proporcionada por FSharp.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="23ba3-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="23ba3-250">Del mismo modo, una biblioteca de estadísticas podría incluir un módulo con funciones `erf` y `erfc`, donde este módulo está diseñado para que se abran explícitamente o automáticamente.</span><span class="sxs-lookup"><span data-stu-id="23ba3-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="23ba3-251">Considere el uso de RequireQualifiedAccess y aplicar con cuidado AutoOpen atributos</span><span class="sxs-lookup"><span data-stu-id="23ba3-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="23ba3-252">Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que no se puede abrir el módulo y que las referencias a los elementos del módulo requieren explícita calificar el acceso.</span><span class="sxs-lookup"><span data-stu-id="23ba3-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="23ba3-253">Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.</span><span class="sxs-lookup"><span data-stu-id="23ba3-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="23ba3-254">Esto es útil cuando las funciones y los valores del módulo tienen nombres que es probables que entran en conflicto con los nombres de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="23ba3-255">Necesidad de tener acceso completo puede aumentar considerablemente el mantenimiento a largo plazo y la capacidad de evolución de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="23ba3-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="23ba3-256">Agregar el `[<AutoOpen>]` atributo a un módulo, significa que el módulo se abrirá cuando se abre el espacio de nombres contenedor.</span><span class="sxs-lookup"><span data-stu-id="23ba3-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="23ba3-257">El `[<AutoOpen>]` el atributo puede aplicarse a un ensamblado para indicar un módulo que se abre automáticamente cuando se hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23ba3-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="23ba3-258">Por ejemplo, una biblioteca de estadísticas **MathsHeaven.Statistics** podría contener un `module MathsHeaven.Statistics.Operators` que contienen funciones `erf` y `erfc`.</span><span class="sxs-lookup"><span data-stu-id="23ba3-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="23ba3-259">Es razonable marcar este módulo como `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="23ba3-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="23ba3-260">Esto significa `open MathsHeaven.Statistics` también abrirá este módulo y poner los nombres `erf` y `erfc` en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="23ba3-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="23ba3-261">Otro buen uso de `[<AutoOpen>]` es para los módulos que contienen métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="23ba3-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="23ba3-262">Uso excesivo de `[<AutoOpen>]` clientes potenciales a contaminado espacios de nombres y el atributo deberían usarse con cuidado.</span><span class="sxs-lookup"><span data-stu-id="23ba3-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="23ba3-263">Para las bibliotecas específicas de dominios concretos, un uso razonable de `[<AutoOpen>]` puede dar lugar a una mejor utilización.</span><span class="sxs-lookup"><span data-stu-id="23ba3-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="23ba3-264">Considere la posibilidad de definir los miembros de operador en las clases donde es adecuado utilizar operadores conocidos</span><span class="sxs-lookup"><span data-stu-id="23ba3-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="23ba3-265">A veces clases se utilizan para modelar matemáticas construcciones como vectores.</span><span class="sxs-lookup"><span data-stu-id="23ba3-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="23ba3-266">Cuando el dominio que se está modelando tiene operadores conocidos, que definirlas como miembros intrínsecos a la clase es útil.</span><span class="sxs-lookup"><span data-stu-id="23ba3-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="23ba3-267">Esta guía se corresponde con las instrucciones generales de .NET para estos tipos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="23ba3-268">Sin embargo, puede ser importante además en F# codificaciones, ya que esto permite que estos tipos para usarse en métodos con restricciones de miembro, como List.sumBy y junto con las funciones de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="23ba3-269">Considere el uso de CompiledName para proporcionar una. Nombre descriptivo de la red para otros consumidores de idioma de .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="23ba3-270">En ocasiones, puede nombrar algo en un estilo para los consumidores de F# (por ejemplo, un miembro estático en minúsculas para que aparezca como si fuera una función de módulo enlazados), pero tienen un estilo diferente para el nombre cuando se compila en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23ba3-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="23ba3-271">Puede usar el `[<CompiledName>]` atributo para proporcionar un estilo diferente de F# que no es código que consume el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23ba3-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="23ba3-272">Mediante el uso de `[<CompiledName>]`, puede usar las convenciones de nomenclatura .NET para F# que no son los consumidores del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23ba3-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="23ba3-273">Use la sobrecarga de métodos para funciones miembro, si al hacerlo proporciona una API más sencilla</span><span class="sxs-lookup"><span data-stu-id="23ba3-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="23ba3-274">La sobrecarga de método es una herramienta eficaz para simplificar una API que puede necesitar realizar una funcionalidad similar, pero con distintas opciones o argumentos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="23ba3-275">En F#, es más habitual de sobrecarga en el número de argumentos en lugar de tipos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="23ba3-276">Ocultar las representaciones de registro y los tipos de unión si es probable que evolucione el diseño de estos tipos</span><span class="sxs-lookup"><span data-stu-id="23ba3-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="23ba3-277">Evitar revelar representaciones concretas de objetos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="23ba3-278">Por ejemplo, la representación concreta de <xref:System.DateTime> la API pública externa del diseño de biblioteca de .NET no revelan los valores.</span><span class="sxs-lookup"><span data-stu-id="23ba3-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="23ba3-279">En tiempo de ejecución, Common Language Runtime sabe la implementación confirma que se usará en toda la ejecución.</span><span class="sxs-lookup"><span data-stu-id="23ba3-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="23ba3-280">Sin embargo, código compilado no propio recoge las dependencias de la representación concreta.</span><span class="sxs-lookup"><span data-stu-id="23ba3-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="23ba3-281">Evite el uso de la herencia de implementación para la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="23ba3-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="23ba3-282">En F#, rara vez se usa la herencia de la implementación.</span><span class="sxs-lookup"><span data-stu-id="23ba3-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="23ba3-283">Además, las jerarquías de herencia son a menudo complejo y difícil de cambiar cuando lleguen nuevos requisitos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="23ba3-284">Implementación de la herencia sigue existiendo en F# de compatibilidad y raras ocasiones donde es la mejor solución a un problema, pero deben buscarse técnicas alternativas en los programas de F# cuando se diseña para polimorfismo, como la implementación de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="23ba3-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="23ba3-285">Firmas de función y miembro</span><span class="sxs-lookup"><span data-stu-id="23ba3-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="23ba3-286">Uso de tuplas para los valores devueltos cuando se devuelve un número pequeño de varios valores no relacionados</span><span class="sxs-lookup"><span data-stu-id="23ba3-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="23ba3-287">Este es un buen ejemplo del uso de una tupla en un tipo de valor devuelto:</span><span class="sxs-lookup"><span data-stu-id="23ba3-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="23ba3-288">Para devolver tipos que contengan muchos componentes, o donde los componentes están relacionados con una sola entidad identificable, plantéese el uso de un tipo con nombre en lugar de una tupla.</span><span class="sxs-lookup"><span data-stu-id="23ba3-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="23ba3-289">Use `Async<T>` para programación asincrónica en los límites de API de F#</span><span class="sxs-lookup"><span data-stu-id="23ba3-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="23ba3-290">Si hay una operación sincrónica correspondiente denominada `Operation` que devuelve un `T`, a continuación, la operación asincrónica debe denominarse `AsyncOperation` si devuelve `Async<T>` o `OperationAsync` si devuelve `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="23ba3-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="23ba3-291">Para los tipos de .NET utilizados frecuentemente que exponen métodos Begin/End, considere el uso de `Async.FromBeginEnd` escribir métodos de extensión como una fachada para proporcionar la F# async modelo de programación a las API de .NET.</span><span class="sxs-lookup"><span data-stu-id="23ba3-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

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

### <a name="exceptions"></a><span data-ttu-id="23ba3-292">Excepciones</span><span class="sxs-lookup"><span data-stu-id="23ba3-292">Exceptions</span></span>

<span data-ttu-id="23ba3-293">Consulte [administración de errores](conventions.md#error-management) para obtener información sobre el uso adecuado de las excepciones, los resultados y opciones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-293">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="23ba3-294">Miembros de extensión</span><span class="sxs-lookup"><span data-stu-id="23ba3-294">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="23ba3-295">Aplicar con cuidado los miembros de extensión de F# en F#-a-F# componentes</span><span class="sxs-lookup"><span data-stu-id="23ba3-295">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="23ba3-296">Los miembros de extensión de F# por lo general deben usarse solo para las operaciones que se encuentran en el cierre de operaciones intrínsecos asociado con un tipo en la mayoría de los modos de uso.</span><span class="sxs-lookup"><span data-stu-id="23ba3-296">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="23ba3-297">Un uso común es proporcionar las API que son más idiomáticas de F# para varios tipos. NET:</span><span class="sxs-lookup"><span data-stu-id="23ba3-297">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="23ba3-298">Tipos de unión</span><span class="sxs-lookup"><span data-stu-id="23ba3-298">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="23ba3-299">Usar uniones discriminadas en lugar de jerarquías de clases para los datos de la estructura de árbol</span><span class="sxs-lookup"><span data-stu-id="23ba3-299">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="23ba3-300">Las estructuras de árbol están definidos de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="23ba3-300">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="23ba3-301">Esto es difícil con herencia, pero elegante con uniones discriminadas.</span><span class="sxs-lookup"><span data-stu-id="23ba3-301">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="23ba3-302">Que representa los datos en forma de árbol con uniones discriminadas también permite beneficiarse de exhaustiveness en coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-302">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="23ba3-303">Use `[<RequireQualifiedAccess>]` en tipos de unión cuyos nombres casos no son lo suficientemente exclusivos</span><span class="sxs-lookup"><span data-stu-id="23ba3-303">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="23ba3-304">Puede buscar por sí mismo en un dominio donde el mismo nombre es el nombre más adecuado para diferentes operaciones, como casos de unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="23ba3-304">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="23ba3-305">Puede usar `[<RequireQualifiedAccess>]` para eliminar la ambigüedad con el fin de evitar que se produzca errores confusos debido al sombreado dependientes en el orden de los nombres de casos `open` instrucciones</span><span class="sxs-lookup"><span data-stu-id="23ba3-305">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="23ba3-306">Ocultar las representaciones de las uniones discriminadas de API compatibles binarias si es probable que evolucione el diseño de estos tipos</span><span class="sxs-lookup"><span data-stu-id="23ba3-306">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="23ba3-307">Tipos de uniones se basan en F# coincidencia formularios para un modelo de programación conciso.</span><span class="sxs-lookup"><span data-stu-id="23ba3-307">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="23ba3-308">Como se mencionó anteriormente, debe evitar revelar las representaciones de datos concreta si es probable que evolucione el diseño de estos tipos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-308">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="23ba3-309">Por ejemplo, se puede ocultar la representación de una unión discriminada con una declaración interna o privada, o mediante un archivo de signatura.</span><span class="sxs-lookup"><span data-stu-id="23ba3-309">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="23ba3-310">Si revelan las uniones discriminadas forma indiscriminada, le resultará difícil de versión de la biblioteca sin interrumpir el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="23ba3-310">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="23ba3-311">En su lugar, considere la posibilidad de que revelen uno o varios modelos activos para permitir a través de los valores de su tipo de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-311">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="23ba3-312">Modelos activos proporcionan una alternativa para proporcionar a los consumidores de F# al tiempo que evita exponer directamente los tipos de unión de F# de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-312">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="23ba3-313">Las funciones insertadas y restricciones de miembro</span><span class="sxs-lookup"><span data-stu-id="23ba3-313">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="23ba3-314">Definir los algoritmos genéricos numéricos mediante las funciones insertadas con restricciones de miembro implícito y tipos genéricos resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="23ba3-314">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="23ba3-315">Restricciones de miembro aritméticos y las restricciones de comparación de F# son un estándar para la programación en F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-315">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="23ba3-316">Por ejemplo, considere el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="23ba3-316">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="23ba3-317">El tipo de esta función es como sigue:</span><span class="sxs-lookup"><span data-stu-id="23ba3-317">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="23ba3-318">Se trata de una función adecuada para una API pública en una biblioteca matemática.</span><span class="sxs-lookup"><span data-stu-id="23ba3-318">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="23ba3-319">Evite el uso de restricciones de miembro para simular las clases de tipos y pato</span><span class="sxs-lookup"><span data-stu-id="23ba3-319">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="23ba3-320">Es posible simular "agacha escribiendo" mediante restricciones de miembro de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-320">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="23ba3-321">Sin embargo, los miembros que hacen que utilizar esta propiedad no está en general se debe usar en F#-a-diseños de biblioteca de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-321">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="23ba3-322">Esto es porque los diseños de biblioteca en función de las restricciones implícitas no estándares o desconocidas tienden a producir código de usuario para ser inflexibles y están vinculados al patrón de un marco de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="23ba3-322">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="23ba3-323">Además, hay muchas posibilidades de que un uso intensivo de restricciones de miembro de esta manera puede dar lugar a tiempos de compilación muy largos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-323">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="23ba3-324">Definiciones de operador</span><span class="sxs-lookup"><span data-stu-id="23ba3-324">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="23ba3-325">Evite la definición de operadores simbólicos personalizados</span><span class="sxs-lookup"><span data-stu-id="23ba3-325">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="23ba3-326">Operadores personalizados son esenciales en algunas situaciones y son muy útiles notacionales dispositivos dentro de un gran bloque de código de implementación.</span><span class="sxs-lookup"><span data-stu-id="23ba3-326">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="23ba3-327">Para los nuevos usuarios de una biblioteca, las funciones con nombre suelen ser más fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="23ba3-327">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="23ba3-328">Además, operadores simbólicos personalizados pueden ser difíciles de documento y usuarios les resulta más difícil buscar ayuda sobre operadores, debido a las limitaciones existentes en los motores de IDE y búsqueda.</span><span class="sxs-lookup"><span data-stu-id="23ba3-328">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="23ba3-329">Como resultado, es mejor para su funcionalidad como miembros y funciones con nombre de la publicación y además exponer operadores para esta funcionalidad solo si el beneficio notacional superan a la documentación y el costo de cognitive de disponer de ellos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-329">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="23ba3-330">Unidades de medida</span><span class="sxs-lookup"><span data-stu-id="23ba3-330">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="23ba3-331">Usar cuidadosamente las unidades de medida de seguridad de tipos se ha agregado código de F#</span><span class="sxs-lookup"><span data-stu-id="23ba3-331">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="23ba3-332">Información adicional de escritura para las unidades de medida se borra cuando se ven por otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="23ba3-332">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="23ba3-333">Tenga en cuenta que reflexión, herramientas y componentes .NET verán tipos sans unidades.</span><span class="sxs-lookup"><span data-stu-id="23ba3-333">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="23ba3-334">Por ejemplo, verá los consumidores de C# `float` lugar `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="23ba3-334">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="23ba3-335">Abreviaturas de tipo</span><span class="sxs-lookup"><span data-stu-id="23ba3-335">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="23ba3-336">Utilizar con cuidado las abreviaturas de tipo para simplificar el código de F#</span><span class="sxs-lookup"><span data-stu-id="23ba3-336">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="23ba3-337">Reflexión, herramientas y componentes de .NET no verán los nombres abreviados para los tipos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-337">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="23ba3-338">Un uso significativo de abreviaturas de tipo también puede hacer que un dominio aparezca más complejo de lo es en realidad, lo que podría ser confuso para los consumidores.</span><span class="sxs-lookup"><span data-stu-id="23ba3-338">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="23ba3-339">Evitar las abreviaturas de tipo para tipos públicos cuyos miembros y propiedades deben ser intrínsecamente diferentes a los que están disponibles en el tipo que se va a abreviar</span><span class="sxs-lookup"><span data-stu-id="23ba3-339">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="23ba3-340">En este caso, el tipo que se va a abreviar revela demasiado sobre la representación del tipo real que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="23ba3-340">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="23ba3-341">En su lugar, considere la posibilidad de ajustar la abreviatura en un tipo de clase o una unión discriminada de caso único (o bien, cuando el rendimiento es esencial, considere el uso de un tipo de estructura para ajustar la abreviatura).</span><span class="sxs-lookup"><span data-stu-id="23ba3-341">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="23ba3-342">Por ejemplo, es tentador para definir un mapa múltiple como un caso especial de un mapa de F#, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="23ba3-342">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="23ba3-343">Sin embargo, las operaciones lógicas de notación de puntos en este tipo no son los mismos que las operaciones en un mapa: por ejemplo, es razonable que se asignan el operador de búsqueda. la lista vacía si la clave no está en el diccionario, en lugar de producir una excepción de devolución [clave].</span><span class="sxs-lookup"><span data-stu-id="23ba3-343">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="23ba3-344">Directrices para las bibliotecas para su uso desde otros lenguajes de .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-344">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="23ba3-345">Cuando diseñe bibliotecas para su uso desde otros lenguajes. NET, es muy importante seguir el [instrucciones de diseño de bibliotecas de .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="23ba3-345">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="23ba3-346">En este documento, estas bibliotecas se etiquetan como vainilla bibliotecas. NET, en lugar de F#-orientado a las bibliotecas que usar F# construye sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="23ba3-346">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="23ba3-347">Diseñar vainilla bibliotecas de .NET significa que proporciona las API familiares e idiomáticas coherentes con el resto de .NET Framework, ya que minimiza el uso de F#-construcciones específicas de la API pública.</span><span class="sxs-lookup"><span data-stu-id="23ba3-347">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="23ba3-348">Las reglas se explican en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="23ba3-348">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="23ba3-349">Namespace y el tipo de diseño (para las bibliotecas para su uso desde otros lenguajes. NET)</span><span class="sxs-lookup"><span data-stu-id="23ba3-349">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="23ba3-350">Se aplican las convenciones de nomenclatura de .NET a la API pública de los componentes</span><span class="sxs-lookup"><span data-stu-id="23ba3-350">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="23ba3-351">Preste especial atención al uso de abreviaturas de nombres y las directrices de mayúsculas y minúsculas. NET.</span><span class="sxs-lookup"><span data-stu-id="23ba3-351">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="23ba3-352">Usar espacios de nombres, tipos y miembros como la estructura organizativa principal para los componentes de</span><span class="sxs-lookup"><span data-stu-id="23ba3-352">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="23ba3-353">Todos los archivos que contiene la funcionalidad pública deben comenzar con un `namespace` declaración y las únicas entidades orientados al público en espacios de nombres deben ser tipos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-353">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="23ba3-354">No utilice los módulos de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-354">Do not use F# modules.</span></span>

<span data-ttu-id="23ba3-355">Utilice los módulos que no sean públicos para contener código de implementación, utilidad tipos y funciones de utilidad.</span><span class="sxs-lookup"><span data-stu-id="23ba3-355">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="23ba3-356">Los tipos estáticos debe preferirse a través de módulos, ya que permiten para la futura evolución de la API para usar la sobrecarga y otros conceptos de diseño de API de .NET que no se pueden usar dentro de los módulos de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-356">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="23ba3-357">Por ejemplo, en lugar de la API pública de la siguiente:</span><span class="sxs-lookup"><span data-stu-id="23ba3-357">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="23ba3-358">Tenga en cuenta en su lugar:</span><span class="sxs-lookup"><span data-stu-id="23ba3-358">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="23ba3-359">Usar tipos de registro de F# en las API de .NET de vainilla si el diseño de los tipos no evolucionan</span><span class="sxs-lookup"><span data-stu-id="23ba3-359">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="23ba3-360">Tipos de registro de F# se compilan en una clase .NET simple.</span><span class="sxs-lookup"><span data-stu-id="23ba3-360">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="23ba3-361">Estos son adecuados para algunos tipos simples y estables en las API.</span><span class="sxs-lookup"><span data-stu-id="23ba3-361">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="23ba3-362">Puede utilizar el `[<NoEquality>]` y `[<NoComparison>]` atributos para suprimir la generación automática de interfaces.</span><span class="sxs-lookup"><span data-stu-id="23ba3-362">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="23ba3-363">También evite usar campos de registro mutable de vainilla las API de .NET como estos expone un campo público.</span><span class="sxs-lookup"><span data-stu-id="23ba3-363">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="23ba3-364">Siempre tenga en cuenta si una clase proporcionaría una opción más flexible para la futura evolución de la API.</span><span class="sxs-lookup"><span data-stu-id="23ba3-364">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="23ba3-365">Por ejemplo, el siguiente código de F# expone la API pública a un consumidor de C#:</span><span class="sxs-lookup"><span data-stu-id="23ba3-365">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="23ba3-366">F#:</span><span class="sxs-lookup"><span data-stu-id="23ba3-366">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="23ba3-367">C#:</span><span class="sxs-lookup"><span data-stu-id="23ba3-367">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="23ba3-368">Ocultar la representación de tipos de unión de F# de vainilla las API de .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-368">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="23ba3-369">Tipos de unión de F# no se usan habitualmente en los límites del componente, incluso para F#-a-F# de codificación.</span><span class="sxs-lookup"><span data-stu-id="23ba3-369">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="23ba3-370">Son un dispositivo de implementación excelente cuando se usa internamente en componentes y bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="23ba3-370">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="23ba3-371">Al diseñar una API de .NET de vainilla, considere la posibilidad de ocultar la representación de un tipo de unión mediante una declaración privada o un archivo de signatura.</span><span class="sxs-lookup"><span data-stu-id="23ba3-371">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="23ba3-372">También puede aumentar los tipos que usan una representación de unión internamente con miembros para proporcionar un deseado. API de NET orientadas.</span><span class="sxs-lookup"><span data-stu-id="23ba3-372">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="23ba3-373">Diseño de interfaz gráfica de usuario y otros componentes con los patrones de diseño de framework</span><span class="sxs-lookup"><span data-stu-id="23ba3-373">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="23ba3-374">Hay muchos marcos en. NET, como ASP.NET, WPF y WinForms.</span><span class="sxs-lookup"><span data-stu-id="23ba3-374">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="23ba3-375">Si va a diseñar los componentes para su uso en estos marcos de trabajo, se deben usar las convenciones de nomenclatura y diseño para cada uno.</span><span class="sxs-lookup"><span data-stu-id="23ba3-375">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="23ba3-376">Por ejemplo, para la programación en WPF, adopte los patrones de diseño WPF para las clases que se está diseñando.</span><span class="sxs-lookup"><span data-stu-id="23ba3-376">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="23ba3-377">Para los modelos de programación de la interfaz de usuario, usar patrones de diseño, como los eventos y las colecciones basadas en la notificación como las que se encuentran en <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="23ba3-377">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="23ba3-378">Diseño de objeto y miembro (para las bibliotecas para su uso desde otros lenguajes. NET)</span><span class="sxs-lookup"><span data-stu-id="23ba3-378">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="23ba3-379">Usar CLIEvent (atributo) para exponer los eventos de .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-379">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="23ba3-380">Construir un `DelegateEvent` con específica de .NET de tipo que toma un objeto de delegado y `EventArgs` (en lugar de un `Event`, que simplemente utiliza el `FSharpHandler` tipo de forma predeterminada) para que se publican los eventos de la manera familiar para otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="23ba3-380">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

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

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="23ba3-381">Exponer operaciones asincrónicas, como los métodos que devuelven tareas de .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-381">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="23ba3-382">Las tareas se usan en .NET para representar los cálculos asincrónicos activos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-382">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="23ba3-383">Las tareas son en general menos composicional que F# `Async<T>` objetos, ya que representan tareas "ya está ejecutando" y no pueden componerse entre sí de maneras que realizar la composición paralela o que ocultar la propagación de las señales de cancelación y otros parámetros contextuales.</span><span class="sxs-lookup"><span data-stu-id="23ba3-383">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="23ba3-384">Sin embargo, a pesar de esto, los métodos que devuelven tareas son la representación estándar de la programación asincrónica en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="23ba3-384">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="23ba3-385">Con frecuencia tendrá también desea aceptar un token de cancelación explícito:</span><span class="sxs-lookup"><span data-stu-id="23ba3-385">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="23ba3-386">Usar tipos de delegados de .NET en lugar de tipos de función de F#</span><span class="sxs-lookup"><span data-stu-id="23ba3-386">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="23ba3-387">Aquí, "tipos de función de F#" significan "flecha" tipos como `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="23ba3-387">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="23ba3-388">En lugar de esto:</span><span class="sxs-lookup"><span data-stu-id="23ba3-388">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="23ba3-389">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23ba3-389">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="23ba3-390">El tipo de función de F# aparece como `class FSharpFunc<T,U>` para otros lenguajes. NET y es menos adecuada para las características del lenguaje y las herramientas que comprender los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="23ba3-390">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="23ba3-391">Al crear un método de orden superior como destino .NET Framework 3.5 o posterior, el `System.Func` y `System.Action` los delegados son las API de derechos a publicar para permitir que los desarrolladores de .NET consumir estas API de una manera de baja fricción.</span><span class="sxs-lookup"><span data-stu-id="23ba3-391">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="23ba3-392">(Cuando el destino es .NET Framework 2.0, los tipos de delegado definido por el sistema son más limitados; considere el uso de tipos de delegado predefinido, como `System.Converter<T,U>` o definir un tipo delegado específico.)</span><span class="sxs-lookup"><span data-stu-id="23ba3-392">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="23ba3-393">En el otro lado, los delegados de .NET no son naturales para F#-orientado a las bibliotecas (consulte la sección siguiente sobre F#-orientado a las bibliotecas).</span><span class="sxs-lookup"><span data-stu-id="23ba3-393">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="23ba3-394">Como resultado, es una estrategia de implementación común al desarrollar métodos de orden superior para vainilla bibliotecas de .NET crear toda la implementación mediante los tipos de función de F# y, a continuación, crear la API pública de uso de delegados como una fachada delgada encima real F# implementación de.</span><span class="sxs-lookup"><span data-stu-id="23ba3-394">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="23ba3-395">Usar el patrón de TryGetValue en lugar de devolver los valores de opción de F# y prefiere la sobrecarga de método para tomar los valores de opción de F# como argumentos</span><span class="sxs-lookup"><span data-stu-id="23ba3-395">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="23ba3-396">Patrones comunes de uso para el tipo de opción de F# en las API son mejores implementado en vainilla técnicas de diseño de las API de .NET con .NET standard.</span><span class="sxs-lookup"><span data-stu-id="23ba3-396">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="23ba3-397">En lugar de devolver un valor de opción de F#, considere el uso del tipo de valor devuelto bool además de un parámetro de salida como se muestra en el patrón "TryGetValue".</span><span class="sxs-lookup"><span data-stu-id="23ba3-397">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="23ba3-398">Y, en lugar de tomar valores de opción de F# como parámetros, considere el uso de la sobrecarga de métodos o argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="23ba3-398">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="23ba3-399">Usar la interfaz de colección .NET tipos IEnumerable\<T\> e IDictionary\<clave, valor\> para los parámetros y valores devueltos</span><span class="sxs-lookup"><span data-stu-id="23ba3-399">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="23ba3-400">Evite el uso de tipos de colección concretos, como matrices .NET `T[]`, tipos de F# `list<T>`, `Map<Key,Value>` y `Set<T>`, y tipos de colección concretos. NET, como `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="23ba3-400">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="23ba3-401">Las instrucciones de diseño de la biblioteca de .NET tienen buenos consejos sobre cuándo usar diversos tipos de colecciones como `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="23ba3-401">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="23ba3-402">Algún uso de matrices (`T[]`) es aceptable en algunas circunstancias, por motivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="23ba3-402">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="23ba3-403">Tenga en cuenta especialmente que `seq<T>` es simplemente la F# alias de `IEnumerable<T>`, y, por tanto, a menudo es un tipo adecuado para una API de .NET de vainilla seq.</span><span class="sxs-lookup"><span data-stu-id="23ba3-403">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="23ba3-404">En lugar de la lista de F#:</span><span class="sxs-lookup"><span data-stu-id="23ba3-404">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="23ba3-405">Use las secuencias de F#:</span><span class="sxs-lookup"><span data-stu-id="23ba3-405">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="23ba3-406">Usar el tipo de unidad como el único tipo de entrada de un método para definir un método de argumento de cero, o como el único tipo para definir un método que devuelve void de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23ba3-406">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="23ba3-407">Evitar otros usos del tipo de unidad.</span><span class="sxs-lookup"><span data-stu-id="23ba3-407">Avoid other uses of the unit type.</span></span> <span data-ttu-id="23ba3-408">Estas son buenas:</span><span class="sxs-lookup"><span data-stu-id="23ba3-408">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="23ba3-409">Esto es incorrecto:</span><span class="sxs-lookup"><span data-stu-id="23ba3-409">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="23ba3-410">Comprobar si hay valores null en los límites de API de .NET básica</span><span class="sxs-lookup"><span data-stu-id="23ba3-410">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="23ba3-411">Código de implementación de F# suele tener menos valores null, debido a los patrones de diseño inmutable y restricciones de uso de literales null para los tipos de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-411">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="23ba3-412">Otros lenguajes de .NET a menudo usan null como valor mucha más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="23ba3-412">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="23ba3-413">Por este motivo, código F# que expone una API de .NET de vainilla debe comprobar los parámetros de null en el límite de API y evitar que estos valores fluye más profunda en el código de implementación de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-413">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="23ba3-414">El `isNull` función o coincidencia de patrones en el `null` se puede usar el patrón.</span><span class="sxs-lookup"><span data-stu-id="23ba3-414">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="23ba3-415">Evite el uso de tuplas como valores devueltos</span><span class="sxs-lookup"><span data-stu-id="23ba3-415">Avoid using tuples as return values</span></span>

<span data-ttu-id="23ba3-416">En su lugar, preferible devolver un tipo con nombre que contiene los datos agregados, o mediante los parámetros de salida para devolver varios valores.</span><span class="sxs-lookup"><span data-stu-id="23ba3-416">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="23ba3-417">Aunque existen tuplas y las tuplas de struct en .NET (incluida la compatibilidad de lenguaje C# para las tuplas de struct), suelen no proporcionará la API ideal y esperada para desarrolladores de .NET.</span><span class="sxs-lookup"><span data-stu-id="23ba3-417">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="23ba3-418">Evite el uso de la currificación de parámetros</span><span class="sxs-lookup"><span data-stu-id="23ba3-418">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="23ba3-419">En su lugar, utilice las convenciones de llamada de .NET ``Method(arg1,arg2,…,argN)``.</span><span class="sxs-lookup"><span data-stu-id="23ba3-419">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="23ba3-420">Sugerencia: Si va a diseñar bibliotecas para su uso en cualquier lenguaje. NET, a continuación, hay ningún sustituto para realmente hacer algunas experimental C# y Visual Basic de programación para asegurarse de que las bibliotecas de "la frase derecha" de estos lenguajes.</span><span class="sxs-lookup"><span data-stu-id="23ba3-420">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="23ba3-421">También puede usar herramientas como .NET Reflector y del Examinador de objetos de Visual Studio para asegurarse de que las bibliotecas y su documentación aparecen según lo esperado para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="23ba3-421">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="23ba3-422">Apéndice</span><span class="sxs-lookup"><span data-stu-id="23ba3-422">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="23ba3-423">Ejemplo to-end del diseño de código de F# para su uso por otros lenguajes de .NET</span><span class="sxs-lookup"><span data-stu-id="23ba3-423">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="23ba3-424">Tenga en cuenta la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="23ba3-424">Consider the following class:</span></span>

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

<span data-ttu-id="23ba3-425">El tipo F# deducido de esta clase es como sigue:</span><span class="sxs-lookup"><span data-stu-id="23ba3-425">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="23ba3-426">Echemos un vistazo a cómo aparece este tipo de F# para un programador que use otro lenguaje. NET.</span><span class="sxs-lookup"><span data-stu-id="23ba3-426">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="23ba3-427">Por ejemplo, aproximado de C# "firma" es como sigue:</span><span class="sxs-lookup"><span data-stu-id="23ba3-427">For example, the approximate C# “signature” is as follows:</span></span>

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

<span data-ttu-id="23ba3-428">Hay algunos puntos importantes a tener en cuenta acerca de cómo F# representa construcciones aquí.</span><span class="sxs-lookup"><span data-stu-id="23ba3-428">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="23ba3-429">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="23ba3-429">For example:</span></span>

* <span data-ttu-id="23ba3-430">Se ha conservado los metadatos como nombres de argumento.</span><span class="sxs-lookup"><span data-stu-id="23ba3-430">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="23ba3-431">Métodos de F# que toman dos argumentos se convierten en métodos de C# que toman dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="23ba3-431">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="23ba3-432">Las funciones y las listas se convierten en las referencias a los tipos correspondientes en la biblioteca de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-432">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="23ba3-433">El código siguiente muestra cómo ajustar este código para tener todo esto en cuenta.</span><span class="sxs-lookup"><span data-stu-id="23ba3-433">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="23ba3-434">El tipo F# inferido del código es como sigue:</span><span class="sxs-lookup"><span data-stu-id="23ba3-434">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="23ba3-435">La firma de C# ahora es como sigue:</span><span class="sxs-lookup"><span data-stu-id="23ba3-435">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="23ba3-436">Las correcciones realizan preparar este tipo para su uso como parte de una biblioteca básica de .NET son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="23ba3-436">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="23ba3-437">Ajustar varios nombres: `Point1`, `n`, `l`, y `f` se convirtió en `RadialPoint`, `count`, `factor`, y `transform`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="23ba3-437">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="23ba3-438">Usa un tipo de valor devuelto de `seq<RadialPoint>` en lugar de `RadialPoint list` cambiando una construcción de la lista mediante `[ ... ]` a una construcción de secuencia mediante `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="23ba3-438">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="23ba3-439">Usa el tipo de delegado .NET `System.Func` en lugar de un tipo de función de F#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-439">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="23ba3-440">Esto facilita mucho más atractiva para consumir en código C#.</span><span class="sxs-lookup"><span data-stu-id="23ba3-440">This makes it far nicer to consume in C# code.</span></span>
