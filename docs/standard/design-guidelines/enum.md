---
title: Diseño de enumeraciones
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c3e89567761367ddcd67078b138c15b982a0d666
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="enum-design"></a><span data-ttu-id="6aa1c-102">Diseño de enumeraciones</span><span class="sxs-lookup"><span data-stu-id="6aa1c-102">Enum Design</span></span>
<span data-ttu-id="6aa1c-103">Las enumeraciones son un tipo especial de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="6aa1c-104">Hay dos tipos de enumeraciones: las enumeraciones simples de enumeraciones y marca.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="6aa1c-105">Las enumeraciones simples representan pequeños conjuntos cerrados de opciones.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="6aa1c-106">Un ejemplo común de la enumeración simple es un conjunto de colores.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="6aa1c-107">Las enumeraciones de indicador están diseñadas para admitir las operaciones bit a bit de los valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="6aa1c-108">Un ejemplo común de la enumeración de marcas es una lista de opciones.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="6aa1c-109">**✓ HACER** utilizar una enumeración para establecimiento inflexible de tipos, parámetros, propiedades y valores que representan conjuntos de valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="6aa1c-110">**✓ HACER** favorecen el uso de una enumeración en lugar de constantes estáticas.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="6aa1c-111">**X DO NOT** utilizar una enumeración para conjuntos abiertos (por ejemplo, la versión del sistema operativo, los nombres de sus amigos, etcetera).</span><span class="sxs-lookup"><span data-stu-id="6aa1c-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="6aa1c-112">**X DO NOT** proporcionar valores de enumeración reservado que se han diseñado para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="6aa1c-113">Solo puede siempre tiene que agregar valores a la enumeración existente en una fase posterior.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="6aa1c-114">Vea [agregar valores a las enumeraciones](#add_value) para obtener más información sobre cómo agregar valores a las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="6aa1c-115">Valores reservados simplemente contamina el conjunto de valores reales y suelen dar lugar a errores de usuario.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="6aa1c-116">**X evitar** exponer públicamente las enumeraciones con un único valor.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="6aa1c-117">Es una práctica común para garantizar la extensibilidad futura de API de C agregar parámetros reservados para las firmas de método.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="6aa1c-118">Estos parámetros reservados se pueden expresar como enumeraciones con un valor único.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="6aa1c-119">No debe realizarse en las API administradas.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="6aa1c-120">Sobrecarga de métodos permite agregar parámetros en versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="6aa1c-121">**X DO NOT** incluir los valores de centinela en las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="6aa1c-122">Aunque a veces son útiles para los desarrolladores de framework, los valores de centinela son confusos para los usuarios de framework.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="6aa1c-123">Se utilizan para realizar un seguimiento del estado de la enumeración en lugar de ser uno de los valores del conjunto representado por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="6aa1c-124">**✓ HACER** proporcionar un valor de cero en enumeraciones simples.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="6aa1c-125">Tenga en cuenta el valor de llamada algo parecido a "Ninguno".</span><span class="sxs-lookup"><span data-stu-id="6aa1c-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="6aa1c-126">Si este valor no es adecuado para esta enumeración determinada, el valor predeterminado más común para la enumeración debe tener asignado el valor subyacente de cero.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="6aa1c-127">**✓ Considere la posibilidad de** con <xref:System.Int32> (el valor predeterminado en la mayoría de lenguajes de programación) como el tipo subyacente de una enumeración, a menos que cualquiera de las acciones siguientes es verdadera:</span><span class="sxs-lookup"><span data-stu-id="6aa1c-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="6aa1c-128">La enumeración es una enumeración de marcas y dispone de más de 32 indicadores o espera tener más en el futuro.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="6aa1c-129">El tipo subyacente debe ser diferente de <xref:System.Int32> para facilitar la interoperabilidad con código no administrado que espera las enumeraciones de tamaño diferente.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="6aa1c-130">Un tipo subyacente de menor tamaño daría como resultado un ahorro sustancial en el espacio.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="6aa1c-131">Si espera que la enumeración se utiliza principalmente como un argumento para el flujo de control, el tamaño hace poca diferencia.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="6aa1c-132">El ahorro de tamaño podría ser importante si:</span><span class="sxs-lookup"><span data-stu-id="6aa1c-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="6aa1c-133">Se espera que la enumeración que se usará como un campo en una estructura muy a menudo se ha creado una instancia o clase.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="6aa1c-134">Se espera que los usuarios para crear matrices de gran tamaño o colecciones de las instancias de enumeración.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="6aa1c-135">Espera un gran número de instancias de la enumeración que se va a serializar.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="6aa1c-136">Para el uso de memoria, tenga en cuenta que los objetos administrados son siempre `DWORD`-alineados, por lo que necesita eficazmente varias enumeraciones u otras estructuras pequeños en una instancia para empaquetar una enumeración con menor para marcar la diferencia, porque el tamaño de la instancia total es siempre Si va a redondear hasta un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="6aa1c-137">**✓ HACER** nombre enumeraciones de indicador con nombres plurales o sintagmas nominales y enumeraciones simples con nombres simples o frases.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="6aa1c-138">**X DO NOT** extender <xref:System.Enum?displayProperty=nameWithType> directamente.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="6aa1c-139"><xref:System.Enum?displayProperty=nameWithType> es un tipo especial que CLR usa para crear enumeraciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="6aa1c-140">La mayoría de lenguajes de programación proporcionan un elemento de programación que proporciona acceso a esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="6aa1c-141">Por ejemplo, en C# el `enum` palabra clave se utiliza para definir una enumeración.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="6aa1c-142">Diseñar enumeraciones de indicador</span><span class="sxs-lookup"><span data-stu-id="6aa1c-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="6aa1c-143">**✓ HACER** aplicar el <xref:System.FlagsAttribute?displayProperty=nameWithType> para las enumeraciones de indicador.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="6aa1c-144">No se aplican este atributo a las enumeraciones simples.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="6aa1c-145">**✓ HACER** use potencias de dos para los valores de enumeración de marca para que puedan combinarse libremente utilizando la operación OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="6aa1c-146">**✓ Considere la posibilidad de** proporcionar valores de enumeración especiales para normalmente usa combinaciones de marcas.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="6aa1c-147">Operaciones bit a bit son un concepto avanzado y no deberían ser necesarias para tareas sencillas.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="6aa1c-148"><xref:System.IO.FileAccess.ReadWrite> es un ejemplo de este tipo de valor especial.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="6aa1c-149">**X evitar** crear enumeraciones de indicador que ciertas combinaciones de valores no son válidos.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="6aa1c-150">**X evitar** utilizando marca los valores de enumeración de cero a menos que el valor representa "se borran todas las marcas" y se denomina de forma adecuada, según lo prescrito por la instrucción siguiente.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="6aa1c-151">**✓ HACER** nombre al valor cero de enumeraciones de marca `None`.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="6aa1c-152">Para una enumeración de marca, el valor siempre debe significar "se borran todos los indicadores".</span><span class="sxs-lookup"><span data-stu-id="6aa1c-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="6aa1c-153">Agregar valor a las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="6aa1c-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="6aa1c-154">Es muy común para detectar que deba agregar valores a una enumeración después de que ya ha enviado.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="6aa1c-155">Hay un posible problema de compatibilidad de aplicaciones cuando el valor recién agregado se devuelve desde una API existente, porque las aplicaciones mal escritas no pueden controlar el nuevo valor correctamente.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="6aa1c-156">**✓ Considere la posibilidad de** agregar valores a las enumeraciones, a pesar de que un pequeño riesgo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="6aa1c-157">Si tiene datos reales sobre incompatibilidades causadas por las adiciones a una enumeración, considere la posibilidad de agregar una nueva API que devuelve los valores antiguos y nuevos y dejar de utilizar la API antigua, que debería devolver solo los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="6aa1c-158">Esto garantizará que las aplicaciones existentes siguen siendo compatibles.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="6aa1c-159">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6aa1c-160">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa1c-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="6aa1c-161">See Also</span></span>  
 [<span data-ttu-id="6aa1c-162">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="6aa1c-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="6aa1c-163">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6aa1c-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
