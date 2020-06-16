---
title: Diseño de enumeraciones
description: Diseño para enumeraciones, que son una clase especial de tipo de valor. Las enumeraciones simples contienen conjuntos pequeños y cerrados de opciones. Las enumeraciones de marcas admiten operaciones bit a bit en valores de enumeración.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: 40a9faf53dc8a03674cd59074244c15cd304bdd2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768542"
---
# <a name="enum-design"></a><span data-ttu-id="b53d9-105">Diseño de enumeraciones</span><span class="sxs-lookup"><span data-stu-id="b53d9-105">Enum Design</span></span>

<span data-ttu-id="b53d9-106">Las enumeraciones son una clase especial de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="b53d9-106">Enums are a special kind of value type.</span></span> <span data-ttu-id="b53d9-107">Hay dos tipos de enumeraciones: enumeraciones simples y enumeraciones de marcas.</span><span class="sxs-lookup"><span data-stu-id="b53d9-107">There are two kinds of enums: simple enums and flag enums.</span></span>

<span data-ttu-id="b53d9-108">Las enumeraciones simples representan pequeños conjuntos cerrados de opciones.</span><span class="sxs-lookup"><span data-stu-id="b53d9-108">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="b53d9-109">Un ejemplo común de la enumeración simple es un conjunto de colores.</span><span class="sxs-lookup"><span data-stu-id="b53d9-109">A common example of the simple enum is a set of colors.</span></span>

<span data-ttu-id="b53d9-110">Las enumeraciones de marca están diseñadas para admitir las operaciones bit a bit en los valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b53d9-110">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="b53d9-111">Un ejemplo común de la enumeración Flags es una lista de opciones.</span><span class="sxs-lookup"><span data-stu-id="b53d9-111">A common example of the flags enum is a list of options.</span></span>

<span data-ttu-id="b53d9-112">✔️ usar una enumeración para escribir de un tipo seguro parámetros, propiedades y valores devueltos que representen conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="b53d9-112">✔️ DO use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>

<span data-ttu-id="b53d9-113">✔️ favorecer el uso de una enumeración en lugar de constantes estáticas.</span><span class="sxs-lookup"><span data-stu-id="b53d9-113">✔️ DO favor using an enum instead of static constants.</span></span>

<span data-ttu-id="b53d9-114">❌No use una enumeración para los conjuntos abiertos (como la versión del sistema operativo, los nombres de sus amigos, etc.).</span><span class="sxs-lookup"><span data-stu-id="b53d9-114">❌ DO NOT use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>

<span data-ttu-id="b53d9-115">❌NO proporcione valores de enumeración reservados que estén pensados para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="b53d9-115">❌ DO NOT provide reserved enum values that are intended for future use.</span></span>

<span data-ttu-id="b53d9-116">Siempre puede simplemente agregar valores a la enumeración existente en una fase posterior.</span><span class="sxs-lookup"><span data-stu-id="b53d9-116">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="b53d9-117">Vea [Agregar valores a enumeraciones](#add_value) para obtener más información sobre cómo agregar valores a las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="b53d9-117">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="b53d9-118">Los valores reservados solo contaminan el conjunto de valores reales y tienden a provocar errores de usuario.</span><span class="sxs-lookup"><span data-stu-id="b53d9-118">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>

<span data-ttu-id="b53d9-119">❌Evite exponer públicamente las enumeraciones con un solo valor.</span><span class="sxs-lookup"><span data-stu-id="b53d9-119">❌ AVOID publicly exposing enums with only one value.</span></span>

<span data-ttu-id="b53d9-120">Una práctica común para garantizar la extensibilidad futura de las API de C es agregar parámetros reservados a las firmas de método.</span><span class="sxs-lookup"><span data-stu-id="b53d9-120">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="b53d9-121">Estos parámetros reservados se pueden expresar como enumeraciones con un único valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b53d9-121">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="b53d9-122">Esto no se debe hacer en las API administradas.</span><span class="sxs-lookup"><span data-stu-id="b53d9-122">This should not be done in managed APIs.</span></span> <span data-ttu-id="b53d9-123">La sobrecarga de métodos permite agregar parámetros en futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="b53d9-123">Method overloading allows adding parameters in future releases.</span></span>

<span data-ttu-id="b53d9-124">❌NO incluya valores Sentinel en las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="b53d9-124">❌ DO NOT include sentinel values in enums.</span></span>

<span data-ttu-id="b53d9-125">Aunque a veces son útiles para los desarrolladores de Framework, los valores de centinela son confusos para los usuarios del marco.</span><span class="sxs-lookup"><span data-stu-id="b53d9-125">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="b53d9-126">Se utilizan para realizar un seguimiento del estado de la enumeración en lugar de ser uno de los valores del conjunto representado por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b53d9-126">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>

<span data-ttu-id="b53d9-127">✔️ proporcione el valor cero en las enumeraciones simples.</span><span class="sxs-lookup"><span data-stu-id="b53d9-127">✔️ DO provide a value of zero on simple enums.</span></span>

<span data-ttu-id="b53d9-128">Considere la posibilidad de llamar a un valor similar a "ninguno".</span><span class="sxs-lookup"><span data-stu-id="b53d9-128">Consider calling the value something like "None."</span></span> <span data-ttu-id="b53d9-129">Si este valor no es adecuado para esta enumeración concreta, se debe asignar el valor subyacente de cero al valor predeterminado más común para la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b53d9-129">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>

<span data-ttu-id="b53d9-130">✔️ considere la posibilidad <xref:System.Int32> de usar (el valor predeterminado en la mayoría de los lenguajes de programación) como el tipo subyacente de una enumeración, a menos que se cumpla alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="b53d9-130">✔️ CONSIDER using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>

- <span data-ttu-id="b53d9-131">La enumeración es una enumeración flags y tiene más de 32 marcas, o espera tener más en el futuro.</span><span class="sxs-lookup"><span data-stu-id="b53d9-131">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>

- <span data-ttu-id="b53d9-132">El tipo subyacente debe ser diferente que <xref:System.Int32> para facilitar la interoperabilidad con código no administrado que espera enumeraciones de tamaño diferente.</span><span class="sxs-lookup"><span data-stu-id="b53d9-132">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>

- <span data-ttu-id="b53d9-133">Un tipo subyacente más pequeño produciría un ahorro sustancial en el espacio.</span><span class="sxs-lookup"><span data-stu-id="b53d9-133">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="b53d9-134">Si espera que la enumeración se use principalmente como un argumento para el flujo de control, el tamaño tiene poca diferencia.</span><span class="sxs-lookup"><span data-stu-id="b53d9-134">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="b53d9-135">El ahorro de tamaño puede ser importante si:</span><span class="sxs-lookup"><span data-stu-id="b53d9-135">The size savings might be significant if:</span></span>

  - <span data-ttu-id="b53d9-136">Se espera que la enumeración se use como un campo en una estructura o clase con instancias muy frecuentes.</span><span class="sxs-lookup"><span data-stu-id="b53d9-136">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>

  - <span data-ttu-id="b53d9-137">Espera que los usuarios creen matrices de gran tamaño o colecciones de las instancias de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b53d9-137">You expect users to create large arrays or collections of the enum instances.</span></span>

  - <span data-ttu-id="b53d9-138">Espera un gran número de instancias de la enumeración que se van a serializar.</span><span class="sxs-lookup"><span data-stu-id="b53d9-138">You expect a large number of instances of the enum to be serialized.</span></span>

<span data-ttu-id="b53d9-139">Para el uso en memoria, tenga en cuenta que los objetos administrados siempre están `DWORD` alineados, por lo que necesitará de forma eficaz varias enumeraciones u otras estructuras pequeñas en una instancia para empaquetar una enumeración más pequeña con con el fin de crear una diferencia, ya que el tamaño total de la instancia se va a redondear siempre a `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="b53d9-139">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>

<span data-ttu-id="b53d9-140">✔️ HACER que las enumeraciones de marcas de nombre tengan sustantivos plural o sintagmas nominales y simples de enumeración con nombres singulares o sintagmas nominales.</span><span class="sxs-lookup"><span data-stu-id="b53d9-140">✔️ DO name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>

<span data-ttu-id="b53d9-141">❌NO se extiende <xref:System.Enum?displayProperty=nameWithType> directamente.</span><span class="sxs-lookup"><span data-stu-id="b53d9-141">❌ DO NOT extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="b53d9-142"><xref:System.Enum?displayProperty=nameWithType>es un tipo especial usado por CLR para crear enumeraciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b53d9-142"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="b53d9-143">La mayoría de los lenguajes de programación proporcionan un elemento de programación que proporciona acceso a esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="b53d9-143">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="b53d9-144">Por ejemplo, en C#, la `enum` palabra clave se usa para definir una enumeración.</span><span class="sxs-lookup"><span data-stu-id="b53d9-144">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>

<a name="design"></a>

### <a name="designing-flag-enums"></a><span data-ttu-id="b53d9-145">Diseño de enumeraciones de marcas</span><span class="sxs-lookup"><span data-stu-id="b53d9-145">Designing Flag Enums</span></span>

<span data-ttu-id="b53d9-146">✔️ aplican <xref:System.FlagsAttribute?displayProperty=nameWithType> a las enumeraciones de marca.</span><span class="sxs-lookup"><span data-stu-id="b53d9-146">✔️ DO apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="b53d9-147">No aplique este atributo a las enumeraciones simples.</span><span class="sxs-lookup"><span data-stu-id="b53d9-147">Do not apply this attribute to simple enums.</span></span>

<span data-ttu-id="b53d9-148">✔️ usar las potencias de dos para los valores de enumeración de marca para que se puedan combinar libremente mediante la operación OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="b53d9-148">✔️ DO use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>

<span data-ttu-id="b53d9-149">✔️ considere la posibilidad de proporcionar valores de enumeración especiales para combinaciones de marcas de uso frecuente.</span><span class="sxs-lookup"><span data-stu-id="b53d9-149">✔️ CONSIDER providing special enum values for commonly used combinations of flags.</span></span>

<span data-ttu-id="b53d9-150">Las operaciones bit a bit son un concepto avanzado y no deben ser necesarias para tareas sencillas.</span><span class="sxs-lookup"><span data-stu-id="b53d9-150">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="b53d9-151"><xref:System.IO.FileAccess.ReadWrite>es un ejemplo de este tipo de valor especial.</span><span class="sxs-lookup"><span data-stu-id="b53d9-151"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>

<span data-ttu-id="b53d9-152">❌Evite crear enumeraciones de marca en las que determinadas combinaciones de valores no sean válidas.</span><span class="sxs-lookup"><span data-stu-id="b53d9-152">❌ AVOID creating flag enums where certain combinations of values are invalid.</span></span>

<span data-ttu-id="b53d9-153">❌Evite usar valores de enumeración de marca de cero, a menos que el valor represente "todas las marcas se borren" y se denomine adecuadamente, como se indica en la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="b53d9-153">❌ AVOID using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>

<span data-ttu-id="b53d9-154">✔️ el nombre del valor cero de las enumeraciones de marcas `None` .</span><span class="sxs-lookup"><span data-stu-id="b53d9-154">✔️ DO name the zero value of flag enums `None`.</span></span> <span data-ttu-id="b53d9-155">En el caso de una enumeración de marca, el valor siempre debe significar "se borran todas las marcas".</span><span class="sxs-lookup"><span data-stu-id="b53d9-155">For a flag enum, the value must always mean "all flags are cleared."</span></span>

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a><span data-ttu-id="b53d9-156">Agregar valor a las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="b53d9-156">Adding Value to Enums</span></span>

<span data-ttu-id="b53d9-157">Es muy habitual detectar que es necesario agregar valores a una enumeración después de que ya se haya enviado.</span><span class="sxs-lookup"><span data-stu-id="b53d9-157">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="b53d9-158">Existe un posible problema de compatibilidad de aplicaciones cuando el valor recién agregado se devuelve de una API existente, ya que es posible que las aplicaciones mal escritas no controlen correctamente el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="b53d9-158">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>

<span data-ttu-id="b53d9-159">✔️ considere la posibilidad de agregar valores a las enumeraciones, a pesar de un pequeño riesgo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b53d9-159">✔️ CONSIDER adding values to enums, despite a small compatibility risk.</span></span>

<span data-ttu-id="b53d9-160">Si tiene datos reales sobre las incompatibilidades de aplicaciones producidas por adiciones a una enumeración, considere la posibilidad de agregar una nueva API que devuelva los valores nuevos y antiguos, y dejar de usar la API anterior, que debería seguir devolviendo solo los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="b53d9-160">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="b53d9-161">Esto garantizará que las aplicaciones existentes sigan siendo compatibles.</span><span class="sxs-lookup"><span data-stu-id="b53d9-161">This will ensure that your existing applications remain compatible.</span></span>

<span data-ttu-id="b53d9-162">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="b53d9-162">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="b53d9-163">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="b53d9-163">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b53d9-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b53d9-164">See also</span></span>

- [<span data-ttu-id="b53d9-165">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="b53d9-165">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="b53d9-166">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="b53d9-166">Framework Design Guidelines</span></span>](index.md)
