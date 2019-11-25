---
title: 'Palabra clave enum: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 639a3a01c9c4da13e0212bd0230acbd2af170b25
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428525"
---
# <a name="enum-c-reference"></a><span data-ttu-id="885b9-102">enum (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="885b9-102">enum (C# Reference)</span></span>

<span data-ttu-id="885b9-103">La palabra clave `enum` se utiliza para declarar una enumeración, un tipo distinto que consiste en un conjunto de constantes con nombre denominado lista de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="885b9-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>

<span data-ttu-id="885b9-104">Normalmente suele ser recomendable definir una enumeración directamente dentro de un espacio de nombres para que todas las clases de dicho espacio puedan tener acceso a esta con la misma facilidad.</span><span class="sxs-lookup"><span data-stu-id="885b9-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="885b9-105">Sin embargo, una enumeración también puede anidarse dentro de una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="885b9-105">However, an enum can also be nested within a class or struct.</span></span>

<span data-ttu-id="885b9-106">De manera predeterminada, el primer enumerador tiene el valor 0 y el valor de cada enumerador sucesivo se incrementa en 1.</span><span class="sxs-lookup"><span data-stu-id="885b9-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="885b9-107">Por ejemplo, en la siguiente enumeración, `Sat` es `0`, `Sun` es `1`, `Mon` es `2`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="885b9-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>

```csharp
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="885b9-108">Los enumeradores pueden usar inicializadores para invalidar los valores predeterminados, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="885b9-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>

```csharp
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="885b9-109">En esta enumeración, la secuencia de elementos debe iniciarse a partir de `1` en lugar de `0`.</span><span class="sxs-lookup"><span data-stu-id="885b9-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="885b9-110">Sin embargo, se recomienda incluir una constante con el valor 0.</span><span class="sxs-lookup"><span data-stu-id="885b9-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="885b9-111">Para obtener más información, vea [Tipos de enumeración](../../programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="885b9-111">For more information, see [Enumeration Types](../../programming-guide/enumeration-types.md).</span></span>

<span data-ttu-id="885b9-112">Cada tipo de enumeración tiene un tipo subyacente, que puede ser cualquier [tipo numérico entero](../builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="885b9-112">Every enumeration type has an underlying type, which can be any [integral numeric type](../builtin-types/integral-numeric-types.md).</span></span> <span data-ttu-id="885b9-113">El tipo [char](../builtin-types/char.md) no puede ser un tipo subyacente de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="885b9-113">The [char](../builtin-types/char.md) type cannot be an underlying type of an enum.</span></span> <span data-ttu-id="885b9-114">El tipo subyacente predeterminado de los elementos de la enumeración es [int](../builtin-types/integral-numeric-types.md). Para declarar una enumeración de otro tipo entero, como [byte](../builtin-types/integral-numeric-types.md), use el carácter de dos puntos después del identificador y escriba a continuación el tipo, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="885b9-114">The default underlying type of enumeration elements is [int](../builtin-types/integral-numeric-types.md). To declare an enum of another integral type, such as [byte](../builtin-types/integral-numeric-types.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>

```csharp
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="885b9-115">A una variable de un tipo de enumeración se le puede asignar cualquier valor en el intervalo del tipo subyacente; los valores no se limitan a las constantes con nombre.</span><span class="sxs-lookup"><span data-stu-id="885b9-115">A variable of an enumeration type can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>

<span data-ttu-id="885b9-116">El valor predeterminado de `enum E` es el valor que produce la expresión `(E)0`.</span><span class="sxs-lookup"><span data-stu-id="885b9-116">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>

> [!NOTE]
> <span data-ttu-id="885b9-117">Un enumerador no puede contener espacios en blanco en su nombre.</span><span class="sxs-lookup"><span data-stu-id="885b9-117">An enumerator cannot contain white space in its name.</span></span>

<span data-ttu-id="885b9-118">El tipo subyacente especifica la cantidad de almacenamiento asignado a cada enumerador.</span><span class="sxs-lookup"><span data-stu-id="885b9-118">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="885b9-119">No obstante, se necesita una conversión explícita para convertir un tipo `enum` a un tipo entero.</span><span class="sxs-lookup"><span data-stu-id="885b9-119">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="885b9-120">Por ejemplo, la siguiente instrucción asigna el enumerador `Sun` a una variable de tipo [int](../builtin-types/integral-numeric-types.md) utilizando una conversión de tipos para convertir de `enum` a `int`.</span><span class="sxs-lookup"><span data-stu-id="885b9-120">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](../builtin-types/integral-numeric-types.md) by using a cast to convert from `enum` to `int`.</span></span>

```csharp
int x = (int)Day.Sun;
```

<span data-ttu-id="885b9-121">Cuando se aplica <xref:System.FlagsAttribute?displayProperty=nameWithType> a una enumeración que contiene algunos elementos que se pueden combinar con una operación `OR` bit a bit, se observará que el atributo afecta al comportamiento de `enum` cuando se utiliza con algunas herramientas.</span><span class="sxs-lookup"><span data-stu-id="885b9-121">When you apply <xref:System.FlagsAttribute?displayProperty=nameWithType> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="885b9-122">Se pueden observar estos cambios al utilizar herramientas tales como los métodos de la clase <xref:System.Console> y el Evaluador de expresiones.</span><span class="sxs-lookup"><span data-stu-id="885b9-122">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="885b9-123">(Vea el tercer ejemplo.)</span><span class="sxs-lookup"><span data-stu-id="885b9-123">(See the third example.)</span></span>

## <a name="robust-programming"></a><span data-ttu-id="885b9-124">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="885b9-124">Robust programming</span></span>

<span data-ttu-id="885b9-125">Como ocurre con cualquier constante, todas las referencias a los valores individuales de una enumeración se convierten en literales numéricos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="885b9-125">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="885b9-126">Esto puede crear posibles problemas de versiones como se describe en [Constantes](../../programming-guide/classes-and-structs/constants.md).</span><span class="sxs-lookup"><span data-stu-id="885b9-126">This can create potential versioning issues as described in [Constants](../../programming-guide/classes-and-structs/constants.md).</span></span>

<span data-ttu-id="885b9-127">La asignación de valores adicionales a nuevas versiones de enumeraciones o el cambio de los valores de los miembros de enumeración en una nueva versión puede producir problemas para el código fuente dependiente.</span><span class="sxs-lookup"><span data-stu-id="885b9-127">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="885b9-128">Los valores enum se utilizan a menudo en instrucciones [switch](switch.md) .</span><span class="sxs-lookup"><span data-stu-id="885b9-128">Enum values often are used in [switch](switch.md) statements.</span></span> <span data-ttu-id="885b9-129">Si los elementos adicionales se han agregado al tipo `enum` , la sección predeterminada de la instrucción switch se puede seleccionar de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="885b9-129">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>

<span data-ttu-id="885b9-130">Si otros desarrolladores utilizan su código, debería proporcionar instrucciones sobre cómo debería reaccionar el código de ellos al agregar nuevos elementos a cualquier tipo `enum` .</span><span class="sxs-lookup"><span data-stu-id="885b9-130">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>

## <a name="example"></a><span data-ttu-id="885b9-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="885b9-131">Example</span></span>

<span data-ttu-id="885b9-132">En el ejemplo siguiente, se declara una enumeración, `Day`.</span><span class="sxs-lookup"><span data-stu-id="885b9-132">In the following example, an enumeration, `Day`, is declared.</span></span> <span data-ttu-id="885b9-133">Dos enumeradores se convierten explícitamente en un número entero y se asignan a variables de número entero.</span><span class="sxs-lookup"><span data-stu-id="885b9-133">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>

[!code-csharp[csrefKeywordsTypes#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#10)]

## <a name="example"></a><span data-ttu-id="885b9-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="885b9-134">Example</span></span>

<span data-ttu-id="885b9-135">En el ejemplo siguiente, la opción de tipo base se utiliza para declarar un `enum` cuyos miembros son del tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="885b9-135">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="885b9-136">Observe que a pesar de que el tipo subyacente de la enumeración es `long`, los miembros de la enumeración todavía deben convertirse explícitamente al tipo `long` mediante una conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="885b9-136">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>

[!code-csharp[csrefKeywordsTypes#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#11)]

## <a name="example"></a><span data-ttu-id="885b9-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="885b9-137">Example</span></span>

<span data-ttu-id="885b9-138">En el ejemplo de código siguiente se ilustra el uso y efecto del atributo <xref:System.FlagsAttribute?displayProperty=nameWithType> en una declaración `enum` .</span><span class="sxs-lookup"><span data-stu-id="885b9-138">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute on an `enum` declaration.</span></span>

[!code-csharp[csrefKeywordsTypes#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#12)]

## <a name="comments"></a><span data-ttu-id="885b9-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="885b9-139">Comments</span></span>

<span data-ttu-id="885b9-140">Si quita `Flags`, el ejemplo muestra los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="885b9-140">If you remove `Flags`, the example displays the following values:</span></span>

`5`

`5`

## <a name="c-language-specification"></a><span data-ttu-id="885b9-141">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="885b9-141">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="885b9-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="885b9-142">See also</span></span>

- [<span data-ttu-id="885b9-143">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="885b9-143">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="885b9-144">Tipos de enumeración</span><span class="sxs-lookup"><span data-stu-id="885b9-144">Enumeration Types</span></span>](../../programming-guide/enumeration-types.md)
- [<span data-ttu-id="885b9-145">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="885b9-145">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="885b9-146">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="885b9-146">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="885b9-147">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="885b9-147">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="885b9-148">Convenciones de nomenclatura de enum</span><span class="sxs-lookup"><span data-stu-id="885b9-148">Enum Naming Conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
