---
title: Diseño de enumeraciones
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: 3b24bfefd3edb0585e9c6369e9b8151b17151661
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741712"
---
# <a name="enum-design"></a><span data-ttu-id="fab3f-102">Diseño de enumeraciones</span><span class="sxs-lookup"><span data-stu-id="fab3f-102">Enum Design</span></span>

<span data-ttu-id="fab3f-103">Las enumeraciones son una clase especial de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="fab3f-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="fab3f-104">Hay dos tipos de enumeraciones: enumeraciones simples y enumeraciones de marcas.</span><span class="sxs-lookup"><span data-stu-id="fab3f-104">There are two kinds of enums: simple enums and flag enums.</span></span>

<span data-ttu-id="fab3f-105">Las enumeraciones simples representan pequeños conjuntos cerrados de opciones.</span><span class="sxs-lookup"><span data-stu-id="fab3f-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="fab3f-106">Un ejemplo común de la enumeración simple es un conjunto de colores.</span><span class="sxs-lookup"><span data-stu-id="fab3f-106">A common example of the simple enum is a set of colors.</span></span>

<span data-ttu-id="fab3f-107">Las enumeraciones de marca están diseñadas para admitir las operaciones bit a bit en los valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="fab3f-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="fab3f-108">Un ejemplo común de la enumeración Flags es una lista de opciones.</span><span class="sxs-lookup"><span data-stu-id="fab3f-108">A common example of the flags enum is a list of options.</span></span>

<span data-ttu-id="fab3f-109">✔️ usar una enumeración para escribir de un tipo seguro parámetros, propiedades y valores devueltos que representen conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="fab3f-109">✔️ DO use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>

<span data-ttu-id="fab3f-110">✔️ favorecer el uso de una enumeración en lugar de constantes estáticas.</span><span class="sxs-lookup"><span data-stu-id="fab3f-110">✔️ DO favor using an enum instead of static constants.</span></span>

<span data-ttu-id="fab3f-111">❌ no usar una enumeración para los conjuntos abiertos (como la versión del sistema operativo, los nombres de sus amigos, etc.).</span><span class="sxs-lookup"><span data-stu-id="fab3f-111">❌ DO NOT use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>

<span data-ttu-id="fab3f-112">❌ no proporcionan valores de enumeración reservados que están pensados para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="fab3f-112">❌ DO NOT provide reserved enum values that are intended for future use.</span></span>

<span data-ttu-id="fab3f-113">Siempre puede simplemente agregar valores a la enumeración existente en una fase posterior.</span><span class="sxs-lookup"><span data-stu-id="fab3f-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="fab3f-114">Vea [Agregar valores a enumeraciones](#add_value) para obtener más información sobre cómo agregar valores a las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="fab3f-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="fab3f-115">Los valores reservados solo contaminan el conjunto de valores reales y tienden a provocar errores de usuario.</span><span class="sxs-lookup"><span data-stu-id="fab3f-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>

<span data-ttu-id="fab3f-116">❌ evitar exponer públicamente las enumeraciones con un solo valor.</span><span class="sxs-lookup"><span data-stu-id="fab3f-116">❌ AVOID publicly exposing enums with only one value.</span></span>

<span data-ttu-id="fab3f-117">Una práctica común para garantizar la extensibilidad futura de las API de C es agregar parámetros reservados a las firmas de método.</span><span class="sxs-lookup"><span data-stu-id="fab3f-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="fab3f-118">Estos parámetros reservados se pueden expresar como enumeraciones con un único valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fab3f-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="fab3f-119">Esto no se debe hacer en las API administradas.</span><span class="sxs-lookup"><span data-stu-id="fab3f-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="fab3f-120">La sobrecarga de métodos permite agregar parámetros en futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="fab3f-120">Method overloading allows adding parameters in future releases.</span></span>

<span data-ttu-id="fab3f-121">❌ no incluyen valores de centinela en las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="fab3f-121">❌ DO NOT include sentinel values in enums.</span></span>

<span data-ttu-id="fab3f-122">Aunque a veces son útiles para los desarrolladores de Framework, los valores de centinela son confusos para los usuarios del marco.</span><span class="sxs-lookup"><span data-stu-id="fab3f-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="fab3f-123">Se utilizan para realizar un seguimiento del estado de la enumeración en lugar de ser uno de los valores del conjunto representado por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="fab3f-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>

<span data-ttu-id="fab3f-124">✔️ proporcione el valor cero en las enumeraciones simples.</span><span class="sxs-lookup"><span data-stu-id="fab3f-124">✔️ DO provide a value of zero on simple enums.</span></span>

<span data-ttu-id="fab3f-125">Considere la posibilidad de llamar a un valor similar a "ninguno".</span><span class="sxs-lookup"><span data-stu-id="fab3f-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="fab3f-126">Si este valor no es adecuado para esta enumeración concreta, se debe asignar el valor subyacente de cero al valor predeterminado más común para la enumeración.</span><span class="sxs-lookup"><span data-stu-id="fab3f-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>

<span data-ttu-id="fab3f-127">✔️ considere la posibilidad de usar <xref:System.Int32> (el valor predeterminado en la mayoría de los lenguajes de programación) como el tipo subyacente de una enumeración, a menos que se cumpla alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="fab3f-127">✔️ CONSIDER using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>

- <span data-ttu-id="fab3f-128">La enumeración es una enumeración flags y tiene más de 32 marcas, o espera tener más en el futuro.</span><span class="sxs-lookup"><span data-stu-id="fab3f-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>

- <span data-ttu-id="fab3f-129">El tipo subyacente debe ser diferente de <xref:System.Int32> para facilitar la interoperabilidad con código no administrado que espera enumeraciones de tamaño diferente.</span><span class="sxs-lookup"><span data-stu-id="fab3f-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>

- <span data-ttu-id="fab3f-130">Un tipo subyacente más pequeño produciría un ahorro sustancial en el espacio.</span><span class="sxs-lookup"><span data-stu-id="fab3f-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="fab3f-131">Si espera que la enumeración se use principalmente como un argumento para el flujo de control, el tamaño tiene poca diferencia.</span><span class="sxs-lookup"><span data-stu-id="fab3f-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="fab3f-132">El ahorro de tamaño puede ser importante si:</span><span class="sxs-lookup"><span data-stu-id="fab3f-132">The size savings might be significant if:</span></span>

  - <span data-ttu-id="fab3f-133">Se espera que la enumeración se use como un campo en una estructura o clase con instancias muy frecuentes.</span><span class="sxs-lookup"><span data-stu-id="fab3f-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>

  - <span data-ttu-id="fab3f-134">Espera que los usuarios creen matrices de gran tamaño o colecciones de las instancias de enumeración.</span><span class="sxs-lookup"><span data-stu-id="fab3f-134">You expect users to create large arrays or collections of the enum instances.</span></span>

  - <span data-ttu-id="fab3f-135">Espera un gran número de instancias de la enumeración que se van a serializar.</span><span class="sxs-lookup"><span data-stu-id="fab3f-135">You expect a large number of instances of the enum to be serialized.</span></span>

<span data-ttu-id="fab3f-136">Para el uso en memoria, tenga en cuenta que los objetos administrados siempre están alineados `DWORD`, por lo que necesita de forma eficaz varias enumeraciones u otras estructuras pequeñas en una instancia para empaquetar una enumeración más pequeña con para crear una diferencia, ya que el tamaño total de la instancia se va a redondear siempre a un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="fab3f-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>

<span data-ttu-id="fab3f-137">✔️ HACER que las enumeraciones de marcas de nombre tengan sustantivos plural o sintagmas nominales y simples de enumeración con nombres singulares o sintagmas nominales.</span><span class="sxs-lookup"><span data-stu-id="fab3f-137">✔️ DO name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>

<span data-ttu-id="fab3f-138">❌ no extienden <xref:System.Enum?displayProperty=nameWithType> directamente.</span><span class="sxs-lookup"><span data-stu-id="fab3f-138">❌ DO NOT extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="fab3f-139"><xref:System.Enum?displayProperty=nameWithType> es un tipo especial que CLR usa para crear enumeraciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fab3f-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="fab3f-140">La mayoría de los lenguajes de programación proporcionan un elemento de programación que proporciona acceso a esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="fab3f-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="fab3f-141">Por ejemplo, en C# la palabra clave `enum` se usa para definir una enumeración.</span><span class="sxs-lookup"><span data-stu-id="fab3f-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>

<a name="design"></a>

### <a name="designing-flag-enums"></a><span data-ttu-id="fab3f-142">Diseño de enumeraciones de marcas</span><span class="sxs-lookup"><span data-stu-id="fab3f-142">Designing Flag Enums</span></span>

<span data-ttu-id="fab3f-143">✔️ aplicar el <xref:System.FlagsAttribute?displayProperty=nameWithType> para marcar enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="fab3f-143">✔️ DO apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="fab3f-144">No aplique este atributo a las enumeraciones simples.</span><span class="sxs-lookup"><span data-stu-id="fab3f-144">Do not apply this attribute to simple enums.</span></span>

<span data-ttu-id="fab3f-145">✔️ usar las potencias de dos para los valores de enumeración de marca para que se puedan combinar libremente mediante la operación OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="fab3f-145">✔️ DO use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>

<span data-ttu-id="fab3f-146">✔️ considere la posibilidad de proporcionar valores de enumeración especiales para combinaciones de marcas de uso frecuente.</span><span class="sxs-lookup"><span data-stu-id="fab3f-146">✔️ CONSIDER providing special enum values for commonly used combinations of flags.</span></span>

<span data-ttu-id="fab3f-147">Las operaciones bit a bit son un concepto avanzado y no deben ser necesarias para tareas sencillas.</span><span class="sxs-lookup"><span data-stu-id="fab3f-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="fab3f-148"><xref:System.IO.FileAccess.ReadWrite> es un ejemplo de este tipo de valor especial.</span><span class="sxs-lookup"><span data-stu-id="fab3f-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>

<span data-ttu-id="fab3f-149">❌ evitar la creación de enumeraciones de marca en las que determinadas combinaciones de valores no son válidas.</span><span class="sxs-lookup"><span data-stu-id="fab3f-149">❌ AVOID creating flag enums where certain combinations of values are invalid.</span></span>

<span data-ttu-id="fab3f-150">❌ evitar el uso de valores de enumeración de marca de cero, a menos que el valor represente "todas las marcas se borren" y se denomine adecuadamente, como se indica en la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="fab3f-150">❌ AVOID using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>

<span data-ttu-id="fab3f-151">✔️ nombre el valor cero de las enumeraciones de marcas `None`.</span><span class="sxs-lookup"><span data-stu-id="fab3f-151">✔️ DO name the zero value of flag enums `None`.</span></span> <span data-ttu-id="fab3f-152">En el caso de una enumeración de marca, el valor siempre debe significar "se borran todas las marcas".</span><span class="sxs-lookup"><span data-stu-id="fab3f-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a><span data-ttu-id="fab3f-153">Agregar valor a las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="fab3f-153">Adding Value to Enums</span></span>

<span data-ttu-id="fab3f-154">Es muy habitual detectar que es necesario agregar valores a una enumeración después de que ya se haya enviado.</span><span class="sxs-lookup"><span data-stu-id="fab3f-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="fab3f-155">Existe un posible problema de compatibilidad de aplicaciones cuando el valor recién agregado se devuelve de una API existente, ya que es posible que las aplicaciones mal escritas no controlen correctamente el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="fab3f-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>

<span data-ttu-id="fab3f-156">✔️ considere la posibilidad de agregar valores a las enumeraciones, a pesar de un pequeño riesgo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="fab3f-156">✔️ CONSIDER adding values to enums, despite a small compatibility risk.</span></span>

<span data-ttu-id="fab3f-157">Si tiene datos reales sobre las incompatibilidades de aplicaciones producidas por adiciones a una enumeración, considere la posibilidad de agregar una nueva API que devuelva los valores nuevos y antiguos, y dejar de usar la API anterior, que debería seguir devolviendo solo los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="fab3f-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="fab3f-158">Esto garantizará que las aplicaciones existentes sigan siendo compatibles.</span><span class="sxs-lookup"><span data-stu-id="fab3f-158">This will ensure that your existing applications remain compatible.</span></span>

<span data-ttu-id="fab3f-159">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="fab3f-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="fab3f-160">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="fab3f-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="fab3f-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="fab3f-161">See also</span></span>

- [<span data-ttu-id="fab3f-162">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="fab3f-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="fab3f-163">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fab3f-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
