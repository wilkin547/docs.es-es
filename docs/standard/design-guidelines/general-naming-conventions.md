---
title: Convenciones generales de nomenclatura
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5e5c09c4db8e65d836c7afc7cb78c1f9e32bab65
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="general-naming-conventions"></a><span data-ttu-id="c7973-102">Convenciones generales de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="c7973-102">General Naming Conventions</span></span>
<span data-ttu-id="c7973-103">Esta sección describe generales convenciones de nomenclatura que se relacionan con la elección de palabras, directrices sobre el uso de las abreviaturas y acrónimos y recomendaciones sobre cómo evitar el uso de nombres específicos del idioma.</span><span class="sxs-lookup"><span data-stu-id="c7973-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="c7973-104">Elección de palabras</span><span class="sxs-lookup"><span data-stu-id="c7973-104">Word Choice</span></span>  
 <span data-ttu-id="c7973-105">**✓ HACER** elegir nombres fácilmente legibles para los identificadores.</span><span class="sxs-lookup"><span data-stu-id="c7973-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="c7973-106">Por ejemplo, una propiedad denominada `HorizontalAlignment` es inglés-lee mejor que `AlignmentHorizontal`.</span><span class="sxs-lookup"><span data-stu-id="c7973-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="c7973-107">**✓ HACER** preferible la legibilidad a la mayor brevedad.</span><span class="sxs-lookup"><span data-stu-id="c7973-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="c7973-108">El nombre de propiedad `CanScrollHorizontally` es mejor que `ScrollableX` (una referencia oculta al eje x).</span><span class="sxs-lookup"><span data-stu-id="c7973-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="c7973-109">**X DO NOT** usar caracteres de subrayado, guiones o caracteres no alfanuméricos.</span><span class="sxs-lookup"><span data-stu-id="c7973-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="c7973-110">**X DO NOT** utilizar la notación húngara.</span><span class="sxs-lookup"><span data-stu-id="c7973-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="c7973-111">**X evitar** utilizando identificadores que están en conflicto con las palabras clave de ampliamente utilizar lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="c7973-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="c7973-112">Según la regla 4 de Common Language Specification (CLS), todos los lenguajes compatibles con deben proporcionar un mecanismo que permite el acceso a elementos con nombre que utiliza una palabra clave de ese idioma como un identificador.</span><span class="sxs-lookup"><span data-stu-id="c7973-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="c7973-113">C#, por ejemplo, utiliza el @ inicio de sesión como un mecanismo de escape en este caso.</span><span class="sxs-lookup"><span data-stu-id="c7973-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="c7973-114">Sin embargo, todavía es una buena idea para evitar palabras clave comunes porque es mucho más difícil de usar un método con la secuencia de escape que uno sin él.</span><span class="sxs-lookup"><span data-stu-id="c7973-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="c7973-115">Uso de las abreviaturas y acrónimos</span><span class="sxs-lookup"><span data-stu-id="c7973-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="c7973-116">**X DO NOT** utilice abreviaturas ni contracciones como parte de los nombres de identificador.</span><span class="sxs-lookup"><span data-stu-id="c7973-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="c7973-117">Por ejemplo, utilice `GetWindow` en lugar de `GetWin`.</span><span class="sxs-lookup"><span data-stu-id="c7973-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="c7973-118">**X DO NOT** usar los acrónimos que no son ampliamente aceptada e incluso si son, solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c7973-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="c7973-119">Evitar los nombres específicos del idioma</span><span class="sxs-lookup"><span data-stu-id="c7973-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="c7973-120">**✓ HACER** utilice nombres con interés semántico en lugar de palabras clave específicas del idioma para los nombres de tipo.</span><span class="sxs-lookup"><span data-stu-id="c7973-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="c7973-121">Por ejemplo, `GetLength` es un nombre más adecuado que `GetInt`.</span><span class="sxs-lookup"><span data-stu-id="c7973-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="c7973-122">**✓ HACER** utilizar un nombre de tipo genérico de CLR, en lugar de un nombre específico del lenguaje, en los casos poco frecuentes cuando un identificador no tiene ningún significado semántico más allá de su tipo.</span><span class="sxs-lookup"><span data-stu-id="c7973-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="c7973-123">Por ejemplo, un método de conversión a <xref:System.Int64> debe denominarse `ToInt64`, no `ToLong` (porque <xref:System.Int64> es un nombre CLR para C#-alias específico `long`).</span><span class="sxs-lookup"><span data-stu-id="c7973-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="c7973-124">En la tabla siguiente presenta varios tipos de base de datos con los nombres de tipo CLR (así como los nombres de tipo correspondiente para C#, Visual Basic y C++).</span><span class="sxs-lookup"><span data-stu-id="c7973-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="c7973-125">C#</span><span class="sxs-lookup"><span data-stu-id="c7973-125">C#</span></span>|<span data-ttu-id="c7973-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7973-126">Visual Basic</span></span>|<span data-ttu-id="c7973-127">C++</span><span class="sxs-lookup"><span data-stu-id="c7973-127">C++</span></span>|<span data-ttu-id="c7973-128">CLR</span><span class="sxs-lookup"><span data-stu-id="c7973-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="c7973-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="c7973-129">**sbyte**</span></span>|<span data-ttu-id="c7973-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="c7973-130">**SByte**</span></span>|<span data-ttu-id="c7973-131">**char**</span><span class="sxs-lookup"><span data-stu-id="c7973-131">**char**</span></span>|<span data-ttu-id="c7973-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="c7973-132">**SByte**</span></span>|  
|<span data-ttu-id="c7973-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="c7973-133">**byte**</span></span>|<span data-ttu-id="c7973-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="c7973-134">**Byte**</span></span>|<span data-ttu-id="c7973-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="c7973-135">**unsigned char**</span></span>|<span data-ttu-id="c7973-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="c7973-136">**Byte**</span></span>|  
|<span data-ttu-id="c7973-137">**short**</span><span class="sxs-lookup"><span data-stu-id="c7973-137">**short**</span></span>|<span data-ttu-id="c7973-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="c7973-138">**Short**</span></span>|<span data-ttu-id="c7973-139">**short**</span><span class="sxs-lookup"><span data-stu-id="c7973-139">**short**</span></span>|<span data-ttu-id="c7973-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="c7973-140">**Int16**</span></span>|  
|<span data-ttu-id="c7973-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="c7973-141">**ushort**</span></span>|<span data-ttu-id="c7973-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="c7973-142">**UInt16**</span></span>|<span data-ttu-id="c7973-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="c7973-143">**unsigned short**</span></span>|<span data-ttu-id="c7973-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="c7973-144">**UInt16**</span></span>|  
|<span data-ttu-id="c7973-145">**int**</span><span class="sxs-lookup"><span data-stu-id="c7973-145">**int**</span></span>|<span data-ttu-id="c7973-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="c7973-146">**Integer**</span></span>|<span data-ttu-id="c7973-147">**int**</span><span class="sxs-lookup"><span data-stu-id="c7973-147">**int**</span></span>|<span data-ttu-id="c7973-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="c7973-148">**Int32**</span></span>|  
|<span data-ttu-id="c7973-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="c7973-149">**uint**</span></span>|<span data-ttu-id="c7973-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="c7973-150">**UInt32**</span></span>|<span data-ttu-id="c7973-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="c7973-151">**unsigned int**</span></span>|<span data-ttu-id="c7973-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="c7973-152">**UInt32**</span></span>|  
|<span data-ttu-id="c7973-153">**long**</span><span class="sxs-lookup"><span data-stu-id="c7973-153">**long**</span></span>|<span data-ttu-id="c7973-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="c7973-154">**Long**</span></span>|<span data-ttu-id="c7973-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="c7973-155">**__int64**</span></span>|<span data-ttu-id="c7973-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="c7973-156">**Int64**</span></span>|  
|<span data-ttu-id="c7973-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="c7973-157">**ulong**</span></span>|<span data-ttu-id="c7973-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="c7973-158">**UInt64**</span></span>|<span data-ttu-id="c7973-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="c7973-159">**unsigned __int64**</span></span>|<span data-ttu-id="c7973-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="c7973-160">**UInt64**</span></span>|  
|<span data-ttu-id="c7973-161">**float**</span><span class="sxs-lookup"><span data-stu-id="c7973-161">**float**</span></span>|<span data-ttu-id="c7973-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="c7973-162">**Single**</span></span>|<span data-ttu-id="c7973-163">**float**</span><span class="sxs-lookup"><span data-stu-id="c7973-163">**float**</span></span>|<span data-ttu-id="c7973-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="c7973-164">**Single**</span></span>|  
|<span data-ttu-id="c7973-165">**double**</span><span class="sxs-lookup"><span data-stu-id="c7973-165">**double**</span></span>|<span data-ttu-id="c7973-166">**Double**</span><span class="sxs-lookup"><span data-stu-id="c7973-166">**Double**</span></span>|<span data-ttu-id="c7973-167">**double**</span><span class="sxs-lookup"><span data-stu-id="c7973-167">**double**</span></span>|<span data-ttu-id="c7973-168">**Double**</span><span class="sxs-lookup"><span data-stu-id="c7973-168">**Double**</span></span>|  
|<span data-ttu-id="c7973-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="c7973-169">**bool**</span></span>|<span data-ttu-id="c7973-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="c7973-170">**Boolean**</span></span>|<span data-ttu-id="c7973-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="c7973-171">**bool**</span></span>|<span data-ttu-id="c7973-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="c7973-172">**Boolean**</span></span>|  
|<span data-ttu-id="c7973-173">**char**</span><span class="sxs-lookup"><span data-stu-id="c7973-173">**char**</span></span>|<span data-ttu-id="c7973-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="c7973-174">**Char**</span></span>|<span data-ttu-id="c7973-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="c7973-175">**wchar_t**</span></span>|<span data-ttu-id="c7973-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="c7973-176">**Char**</span></span>|  
|<span data-ttu-id="c7973-177">**string**</span><span class="sxs-lookup"><span data-stu-id="c7973-177">**string**</span></span>|<span data-ttu-id="c7973-178">**String**</span><span class="sxs-lookup"><span data-stu-id="c7973-178">**String**</span></span>|<span data-ttu-id="c7973-179">**String**</span><span class="sxs-lookup"><span data-stu-id="c7973-179">**String**</span></span>|<span data-ttu-id="c7973-180">**String**</span><span class="sxs-lookup"><span data-stu-id="c7973-180">**String**</span></span>|  
|<span data-ttu-id="c7973-181">**object**</span><span class="sxs-lookup"><span data-stu-id="c7973-181">**object**</span></span>|<span data-ttu-id="c7973-182">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="c7973-182">**Object**</span></span>|<span data-ttu-id="c7973-183">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="c7973-183">**Object**</span></span>|<span data-ttu-id="c7973-184">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="c7973-184">**Object**</span></span>|  
  
 <span data-ttu-id="c7973-185">**✓ HACER** utilizar un nombre común, como `value` o `item`, en lugar de repetir el nombre de tipo, en los casos poco frecuentes cuando un identificador no tiene ningún significado semántico y el tipo del parámetro no es importante.</span><span class="sxs-lookup"><span data-stu-id="c7973-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="c7973-186">Nomenclatura de las nuevas versiones de API existentes</span><span class="sxs-lookup"><span data-stu-id="c7973-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="c7973-187">**✓ HACER** usar un nombre similar a la API anterior al crear nuevas versiones de una API existente.</span><span class="sxs-lookup"><span data-stu-id="c7973-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="c7973-188">Esto ayuda a resaltar la relación entre las API.</span><span class="sxs-lookup"><span data-stu-id="c7973-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="c7973-189">**✓ HACER** prefiera agregar un sufijo, en lugar de un prefijo para indicar una nueva versión de una API existente.</span><span class="sxs-lookup"><span data-stu-id="c7973-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="c7973-190">Esto ayudará a detección al examinar la documentación, o usar Intellisense.</span><span class="sxs-lookup"><span data-stu-id="c7973-190">This will assist discovery when browsing documentation, or using Intellisense.</span></span> <span data-ttu-id="c7973-191">La versión anterior de la API se organizarán cerca de las nuevas API, dado que la mayoría de los exploradores e Intellisense mostrar identificadores en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="c7973-191">The old version of the API will be organized close to the new APIs, because most browsers and Intellisense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="c7973-192">**✓ Considere la posibilidad de** con un identificador nuevo, pero significativo, en lugar de agregar un prefijo o un sufijo.</span><span class="sxs-lookup"><span data-stu-id="c7973-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="c7973-193">**✓ HACER** use un sufijo numérico para indicar una nueva versión de una API existente, especialmente si el nombre de la API existente es el nombre único que tenga sentido (es decir, si es un estándar del sector) y si agregar cualquier significativo sufijo (o cambiar el nombre) no es una aplicación opción de ropriate.</span><span class="sxs-lookup"><span data-stu-id="c7973-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="c7973-194">**X DO NOT** usar "Ex" (u otro similar) sufijo para un identificador distinguir de una versión anterior de la misma API.</span><span class="sxs-lookup"><span data-stu-id="c7973-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="c7973-195">**✓ HACER** utilizar el sufijo "64" al introducir las versiones de API que operan en un entero de 64 bits (un entero largo) en lugar de un entero de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="c7973-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="c7973-196">Solo debe adoptar este enfoque cuando existe la API de 32 bits existente; no lo haga para la nuevas API con solo una versión de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c7973-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="c7973-197">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="c7973-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c7973-198">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c7973-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7973-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7973-199">See Also</span></span>  
 [<span data-ttu-id="c7973-200">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c7973-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="c7973-201">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="c7973-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
