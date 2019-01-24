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
author: KrzysztofCwalina
ms.openlocfilehash: c0645ba1179c4c6fd961b871b3061cd51174f427
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675267"
---
# <a name="enum-design"></a><span data-ttu-id="da737-102">Diseño de enumeraciones</span><span class="sxs-lookup"><span data-stu-id="da737-102">Enum Design</span></span>
<span data-ttu-id="da737-103">Las enumeraciones son un tipo especial de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="da737-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="da737-104">Hay dos tipos de enumeraciones: enumeraciones simples de enumeraciones y marca.</span><span class="sxs-lookup"><span data-stu-id="da737-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="da737-105">Enumeraciones simples representan conjuntos cerrados pequeño de opciones.</span><span class="sxs-lookup"><span data-stu-id="da737-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="da737-106">Un ejemplo común de la enumeración simple es un conjunto de colores.</span><span class="sxs-lookup"><span data-stu-id="da737-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="da737-107">Marca enumeraciones están diseñadas para admitir las operaciones bit a bit de los valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="da737-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="da737-108">Un ejemplo común de la enumeración de marcas es una lista de opciones.</span><span class="sxs-lookup"><span data-stu-id="da737-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="da737-109">**✓ DO** utilizar una enumeración para establecimiento inflexible de tipos, parámetros, propiedades y valores que representan conjuntos de valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="da737-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="da737-110">**✓ DO** favorecen el uso de una enumeración en lugar de constantes estáticas.</span><span class="sxs-lookup"><span data-stu-id="da737-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="da737-111">**X DO NOT** utilizar una enumeración para conjuntos abiertos (por ejemplo, la versión del sistema operativo, los nombres de sus amigos, etcetera).</span><span class="sxs-lookup"><span data-stu-id="da737-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="da737-112">**X DO NOT** proporcionar valores de enumeración reservado que se han diseñado para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="da737-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="da737-113">Simplemente siempre puede agregar valores a la enumeración existente en una etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="da737-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="da737-114">Consulte [agregar valores a enumeraciones](#add_value) para obtener más información sobre cómo agregar valores a las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="da737-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="da737-115">Los valores de reservado simplemente contaminen el conjunto de valores reales y tienden a producir errores de usuario.</span><span class="sxs-lookup"><span data-stu-id="da737-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="da737-116">**X AVOID** exponer públicamente las enumeraciones con un único valor.</span><span class="sxs-lookup"><span data-stu-id="da737-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="da737-117">Es una práctica común para garantizar la futura extensibilidad de C API agregar parámetros reservados para las firmas de método.</span><span class="sxs-lookup"><span data-stu-id="da737-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="da737-118">Estos parámetros reservados pueden expresarse como enumeraciones con un valor predeterminado único.</span><span class="sxs-lookup"><span data-stu-id="da737-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="da737-119">No debe realizarse en las API administradas.</span><span class="sxs-lookup"><span data-stu-id="da737-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="da737-120">Sobrecarga de métodos permite agregar parámetros en futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="da737-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="da737-121">**X DO NOT** incluir los valores de centinela en las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="da737-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="da737-122">Aunque a veces son útiles para los desarrolladores de framework, los valores de centinela son confusos para los usuarios de framework.</span><span class="sxs-lookup"><span data-stu-id="da737-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="da737-123">Se utilizan para realizar un seguimiento del estado de la enumeración en lugar de ser uno de los valores del conjunto representado por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="da737-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="da737-124">**✓ DO** proporcionar un valor de cero en enumeraciones simples.</span><span class="sxs-lookup"><span data-stu-id="da737-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="da737-125">Considere la posibilidad de llamar a algo parecido a "None". el valor</span><span class="sxs-lookup"><span data-stu-id="da737-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="da737-126">Si este valor no es adecuado para esta enumeración determinada, el valor predeterminado más común para la enumeración debe asignarse el valor subyacente cero.</span><span class="sxs-lookup"><span data-stu-id="da737-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="da737-127">**✓ CONSIDER** con <xref:System.Int32> (el valor predeterminado en la mayoría de lenguajes de programación) como el tipo subyacente de una enumeración, a menos que cualquiera de las acciones siguientes es verdadera:</span><span class="sxs-lookup"><span data-stu-id="da737-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="da737-128">La enumeración es una enumeración de marcas y dispone de más de 32 indicadores o espera tener más en el futuro.</span><span class="sxs-lookup"><span data-stu-id="da737-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="da737-129">El tipo subyacente debe ser diferente de <xref:System.Int32> para facilitar la interoperabilidad con código no administrado espera las enumeraciones de diferente tamaño.</span><span class="sxs-lookup"><span data-stu-id="da737-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="da737-130">Un tipo subyacente de menor tamaño daría lugar a importantes ahorros de espacio.</span><span class="sxs-lookup"><span data-stu-id="da737-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="da737-131">Si espera que la enumeración se utiliza principalmente como un argumento para el flujo de control, el tamaño hace poca diferencia.</span><span class="sxs-lookup"><span data-stu-id="da737-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="da737-132">El ahorro de tamaño puede ser considerable si:</span><span class="sxs-lookup"><span data-stu-id="da737-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="da737-133">Esperar la enumeración que se usará como un campo en una estructura con instancias con mucha frecuencia o clase.</span><span class="sxs-lookup"><span data-stu-id="da737-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="da737-134">Se espera que los usuarios para crear matrices de gran tamaño o colecciones de las instancias de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="da737-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="da737-135">Espera un gran número de instancias de la enumeración que se va a serializar.</span><span class="sxs-lookup"><span data-stu-id="da737-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="da737-136">Para el uso de memoria, tenga en cuenta que los objetos administrados son siempre `DWORD`-alineadas, por lo que necesita de forma eficaz varias enumeraciones u otras estructuras pequeño en una instancia para empaquetar una enumeración con más pequeña para marcar la diferencia, porque el tamaño total de instancias siempre es Si va a redondear hasta un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="da737-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="da737-137">**✓ DO** nombre enumeraciones de indicador con nombres plurales o sintagmas nominales y enumeraciones simples con nombres simples o frases.</span><span class="sxs-lookup"><span data-stu-id="da737-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="da737-138">**X DO NOT** extender <xref:System.Enum?displayProperty=nameWithType> directamente.</span><span class="sxs-lookup"><span data-stu-id="da737-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="da737-139"><xref:System.Enum?displayProperty=nameWithType> es un tipo especial que CLR usa para crear enumeraciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="da737-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="da737-140">La mayoría de lenguajes de programación proporcionan un elemento de programación que proporciona acceso a esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="da737-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="da737-141">Por ejemplo, en C# el `enum` palabra clave se usa para definir una enumeración.</span><span class="sxs-lookup"><span data-stu-id="da737-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="da737-142">Diseño de las enumeraciones de marca</span><span class="sxs-lookup"><span data-stu-id="da737-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="da737-143">**✓ DO** aplicar el <xref:System.FlagsAttribute?displayProperty=nameWithType> para las enumeraciones de indicador.</span><span class="sxs-lookup"><span data-stu-id="da737-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="da737-144">No se aplique este atributo a las enumeraciones simples.</span><span class="sxs-lookup"><span data-stu-id="da737-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="da737-145">**✓ DO** use potencias de dos para los valores de enumeración de marca para que puedan combinarse libremente utilizando la operación OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="da737-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="da737-146">**✓ CONSIDER** proporcionar valores de enumeración especiales para normalmente usa combinaciones de marcas.</span><span class="sxs-lookup"><span data-stu-id="da737-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="da737-147">Operaciones bit a bit son un concepto avanzado y no debería requerirse para tareas sencillas.</span><span class="sxs-lookup"><span data-stu-id="da737-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="da737-148"><xref:System.IO.FileAccess.ReadWrite> es un ejemplo de este tipo en un valor especial.</span><span class="sxs-lookup"><span data-stu-id="da737-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="da737-149">**X AVOID** crear enumeraciones de indicador que ciertas combinaciones de valores no son válidos.</span><span class="sxs-lookup"><span data-stu-id="da737-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="da737-150">**X AVOID** utilizando marca los valores de enumeración de cero a menos que el valor representa "se borran todas las marcas" y se denomina de forma adecuada, según lo prescrito por la instrucción siguiente.</span><span class="sxs-lookup"><span data-stu-id="da737-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="da737-151">**✓ DO** nombre al valor cero de enumeraciones de marca `None`.</span><span class="sxs-lookup"><span data-stu-id="da737-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="da737-152">Para una enumeración de marca, el valor siempre debe significar "se borran todas las marcas".</span><span class="sxs-lookup"><span data-stu-id="da737-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="da737-153">Agregar valor a las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="da737-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="da737-154">Es muy común que detecte que son necesarias agregar valores a una enumeración después de que ya se han enviado.</span><span class="sxs-lookup"><span data-stu-id="da737-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="da737-155">Hay un posible problema de compatibilidad de la aplicación cuando el valor recién agregado se devuelve desde una API existente, porque las aplicaciones mal escritas no podrían controlar correctamente el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="da737-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="da737-156">**✓ CONSIDER** agregar valores a las enumeraciones, a pesar de que un pequeño riesgo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="da737-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="da737-157">Si tiene datos reales sobre las incompatibilidades de la aplicación causadas por las adiciones a una enumeración, considere la posibilidad de agregar una nueva API que devuelve los valores nuevos y antiguos y dejar de utilizar la API antigua, que debe continuar devolviendo simplemente los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="da737-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="da737-158">Esto garantizará que las aplicaciones existentes siguen siendo compatibles.</span><span class="sxs-lookup"><span data-stu-id="da737-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="da737-159">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="da737-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="da737-160">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="da737-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da737-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="da737-161">See also</span></span>

- [<span data-ttu-id="da737-162">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="da737-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="da737-163">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="da737-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
