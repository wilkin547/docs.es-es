---
title: 'Tipos de enumeración: referencia de C#'
description: Aprenda sobre los tipos de enumeración de C# que representan una opción o una combinación de opciones.
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: ac4dafef92bbc900d291a5b653c55ba295f1a6d6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093232"
---
# <a name="enumeration-types-c-reference"></a><span data-ttu-id="87813-103">Tipos de enumeración (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="87813-103">Enumeration types (C# reference)</span></span>

<span data-ttu-id="87813-104">Un *tipo de enumeración* es un [tipo de valor](value-types.md) definido por un conjunto de constantes con nombre del tipo [numérico integral](integral-numeric-types.md) subyacente.</span><span class="sxs-lookup"><span data-stu-id="87813-104">An *enumeration type* (or *enum type*) is a [value type](value-types.md) defined by a set of named constants of the underlying [integral numeric](integral-numeric-types.md) type.</span></span> <span data-ttu-id="87813-105">Para definir un tipo de enumeración, use la palabra clave `enum` y especifique los nombres de *miembros de enumeración*:</span><span class="sxs-lookup"><span data-stu-id="87813-105">To define an enumeration type, use the `enum` keyword and specify the names of *enum members*:</span></span>

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

<span data-ttu-id="87813-106">De forma predeterminada, los valores de constante asociados de miembros de enumeración son del tipo `int`; comienzan con cero y aumentan en uno después del orden del texto de la definición.</span><span class="sxs-lookup"><span data-stu-id="87813-106">By default, the associated constant values of enum members are of type `int`; they start with zero and increase by one following the definition text order.</span></span> <span data-ttu-id="87813-107">Puede especificar explícitamente cualquier otro tipo de [numérico entero](integral-numeric-types.md) como un tipo subyacente de un tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="87813-107">You can explicitly specify any other [integral numeric](integral-numeric-types.md) type as an underlying type of an enumeration type.</span></span> <span data-ttu-id="87813-108">También puede especificar explícitamente los valores de constante asociados, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87813-108">You also can explicitly specify the associated constant values, as the following example shows:</span></span>

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

<span data-ttu-id="87813-109">No se puede definir un método dentro de la definición de un tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="87813-109">You cannot define a method inside the definition of an enumeration type.</span></span> <span data-ttu-id="87813-110">Para agregar funcionalidad a un tipo de enumeración, cree un [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="87813-110">To add functionality to an enumeration type, create an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="87813-111">El valor predeterminado de un tipo de enumeración `E` es el valor generado por la expresión `(E)0`, incluso si cero no tiene el miembro de enumeración correspondiente.</span><span class="sxs-lookup"><span data-stu-id="87813-111">The default value of an enumeration type `E` is the value produced by expression `(E)0`, even if zero doesn't have the corresponding enum member.</span></span>

<span data-ttu-id="87813-112">Un tipo de enumeración se usa para representar una opción de un conjunto de valores mutuamente excluyentes o una combinación de opciones.</span><span class="sxs-lookup"><span data-stu-id="87813-112">You use an enumeration type to represent a choice from a set of mutually exclusive values or a combination of choices.</span></span> <span data-ttu-id="87813-113">Para representar una combinación de opciones, defina un tipo de enumeración como marcas de bits.</span><span class="sxs-lookup"><span data-stu-id="87813-113">To represent a combination of choices, define an enumeration type as bit flags.</span></span>

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="87813-114">Tipos de enumeración como marcas de bits</span><span class="sxs-lookup"><span data-stu-id="87813-114">Enumeration types as bit flags</span></span>

<span data-ttu-id="87813-115">Si quiere que un tipo de enumeración represente una combinación de opciones, defina los miembros de enumeración de esas opciones de modo que una opción individual sea un campo de bits.</span><span class="sxs-lookup"><span data-stu-id="87813-115">If you want an enumeration type to represent a combination of choices, define enum members for those choices such that an individual choice is a bit field.</span></span> <span data-ttu-id="87813-116">Es decir, los valores asociados de esos miembros de enumeración deben ser las potencias de dos.</span><span class="sxs-lookup"><span data-stu-id="87813-116">That is, the associated values of those enum members should be the powers of two.</span></span> <span data-ttu-id="87813-117">Luego, puede usar los [operadores lógicos bit a bit`|` o `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) para combinar o formar intersección de combinaciones de opciones, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="87813-117">Then, you can use the [bitwise logical operators `|` or `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) to combine choices or intersect combinations of choices, respectively.</span></span> <span data-ttu-id="87813-118">Para indicar que un tipo de enumeración declara campos de bits, aplíquele el atributo [Flags](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="87813-118">To indicate that an enumeration type declares bit fields, apply the [Flags](xref:System.FlagsAttribute) attribute to it.</span></span> <span data-ttu-id="87813-119">Como se muestra en el ejemplo siguiente, también puede incluir algunas combinaciones típicas en la definición de un tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="87813-119">As the following example shows, you also can include some typical combinations in the definition of an enumeration type.</span></span>

[!code-csharp[enum flags](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Flags)]

<span data-ttu-id="87813-120">Para más información y ver algunos ejemplos, consulte la página de referencia de API de <xref:System.FlagsAttribute?displayProperty=nameWithType> y la sección [miembros no exclusivos y el atributo Flags](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) de la página de referencia de API de <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="87813-120">For more information and examples, see the <xref:System.FlagsAttribute?displayProperty=nameWithType> API reference page and the [Non-exclusive members and the Flags attribute](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) section of the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

## <a name="the-systemenum-type-and-enum-constraint"></a><span data-ttu-id="87813-121">El tipo System.Enum y la restricción de enumeración</span><span class="sxs-lookup"><span data-stu-id="87813-121">The System.Enum type and enum constraint</span></span>

<span data-ttu-id="87813-122">El tipo <xref:System.Enum?displayProperty=nameWithType> es la clase base abstracta de todos los tipos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="87813-122">The <xref:System.Enum?displayProperty=nameWithType> type is the abstract base class of all enumeration types.</span></span> <span data-ttu-id="87813-123">Proporciona una serie de métodos para obtener información sobre un tipo de enumeración y sus valores.</span><span class="sxs-lookup"><span data-stu-id="87813-123">It provides a number of methods to get information about an enumeration type and its values.</span></span> <span data-ttu-id="87813-124">Para más información y ver algunos ejemplos, consulte la página de referencia de la API <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="87813-124">For more information and examples, see the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

<span data-ttu-id="87813-125">A partir C# 7.3, puede usar `System.Enum` en una restricción de clase base (conocida como la [restricción de enumeración](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) para especificar que un parámetro de tipo es un tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="87813-125">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="conversions"></a><span data-ttu-id="87813-126">Conversiones</span><span class="sxs-lookup"><span data-stu-id="87813-126">Conversions</span></span>

<span data-ttu-id="87813-127">Para cualquier tipo de enumeración, existen conversiones explícitas entre el tipo de enumeración y su tipo entero subyacente.</span><span class="sxs-lookup"><span data-stu-id="87813-127">For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type.</span></span> <span data-ttu-id="87813-128">Si convierte (usa[cast](../operators/type-testing-and-cast.md#cast-operator-)) un valor de enumeración a su tipo subyacente, el resultado es el valor entero asociado de un miembro de enumeración.</span><span class="sxs-lookup"><span data-stu-id="87813-128">If you [cast](../operators/type-testing-and-cast.md#cast-operator-) an enum value to its underlying type, the result is the associated integral value of an enum member.</span></span>

[!code-csharp[enum conversions](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Conversions)]

<span data-ttu-id="87813-129">Use el método <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para determinar si un tipo de enumeración contiene un miembro de enumeración con el valor asociado determinado.</span><span class="sxs-lookup"><span data-stu-id="87813-129">Use the <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> method to determine whether an enumeration type contains an enum member with the certain associated value.</span></span>

<span data-ttu-id="87813-130">Para cualquier tipo de enumeración, existen conversiones [boxing y unboxing](../../programming-guide/types/boxing-and-unboxing.md) a y desde el tipo <xref:System.Enum?displayProperty=nameWithType>, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="87813-130">For any enumeration type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.Enum?displayProperty=nameWithType> type, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="87813-131">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="87813-131">C# language specification</span></span>

<span data-ttu-id="87813-132">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="87813-132">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="87813-133">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="87813-133">Enums</span></span>](~/_csharplang/spec/enums.md)
- [<span data-ttu-id="87813-134">Operaciones y valores de enumeración</span><span class="sxs-lookup"><span data-stu-id="87813-134">Enum values and operations</span></span>](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [<span data-ttu-id="87813-135">Operadores lógicos de enumeración</span><span class="sxs-lookup"><span data-stu-id="87813-135">Enumeration logical operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [<span data-ttu-id="87813-136">Operadores de comparación de enumeración</span><span class="sxs-lookup"><span data-stu-id="87813-136">Enumeration comparison operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [<span data-ttu-id="87813-137">Conversiones de enumeración explícitas</span><span class="sxs-lookup"><span data-stu-id="87813-137">Explicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [<span data-ttu-id="87813-138">Conversiones de enumeración implícitas</span><span class="sxs-lookup"><span data-stu-id="87813-138">Implicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a><span data-ttu-id="87813-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="87813-139">See also</span></span>

- [<span data-ttu-id="87813-140">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="87813-140">C# reference</span></span>](../index.md)
- [<span data-ttu-id="87813-141">Cadenas de formato de enumeración</span><span class="sxs-lookup"><span data-stu-id="87813-141">Enumeration format strings</span></span>](../../../standard/base-types/enumeration-format-strings.md)
- [<span data-ttu-id="87813-142">Convenciones de nomenclatura de enumeración</span><span class="sxs-lookup"><span data-stu-id="87813-142">Enum naming conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [<span data-ttu-id="87813-143">switch (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="87813-143">switch statement</span></span>](../keywords/switch.md)
