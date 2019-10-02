---
title: 'Uso de tipos de valor que admiten un valor NULL: Guía de programación de C#'
ms.custom: seodec18
description: Obtenga información sobre cómo trabajar con tipos de valor de C# que admiten valores NULL
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396166"
---
# <a name="using-nullable-value-types-c-programming-guide"></a><span data-ttu-id="9d8b6-103">Uso de tipos de valor que admiten un valor NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9d8b6-103">Using nullable value types (C# Programming Guide)</span></span>

<span data-ttu-id="9d8b6-104">Los tipos de valor que admiten un valor NULL son los que representan todos los valores de un tipo de valor `T` subyacente y un valor [NULL](../../language-reference/keywords/null.md) adicional.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-104">Nullable value types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="9d8b6-105">Para más información, consulte el tema [Tipos de valor que admiten un valor NULL](index.md).</span><span class="sxs-lookup"><span data-stu-id="9d8b6-105">For more information, see the [Nullable value types](index.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="9d8b6-106">C# 8.0 presenta la característica de tipos de referencia que admiten un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-106">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="9d8b6-107">Para más información, consulte [Tipos de referencia que admiten un valor NULL](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="9d8b6-107">For more information, see [Nullable reference types](../../nullable-references.md).</span></span> <span data-ttu-id="9d8b6-108">Los tipos de valor que admiten un valor NULL están disponibles a partir de C# 2.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-108">The nullable value types are available starting with C# 2.</span></span>

<span data-ttu-id="9d8b6-109">Puede hacer referencia a un tipo de valor que admite un valor NULL en cualquiera de las formas intercambiables siguientes: `Nullable<T>` o `T?`.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-109">You can refer to a nullable value type in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="9d8b6-110">`T` debe ser un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-110">`T` must be a value type.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="9d8b6-111">Declaración y asignación</span><span class="sxs-lookup"><span data-stu-id="9d8b6-111">Declaration and assignment</span></span>

<span data-ttu-id="9d8b6-112">Como un tipo de valor se puede convertir de forma implícita al tipo de valor que admite un valor NULL correspondiente, un valor se asigna a un tipo que admite un valor NULL como se haría para su tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-112">As a value type can be implicitly converted to the corresponding nullable value type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="9d8b6-113">También se puede asignar el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-113">You also can assign the `null` value.</span></span> <span data-ttu-id="9d8b6-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-114">For example:</span></span>

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="9d8b6-115">Examen de un valor de tipo que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="9d8b6-115">Examination of a nullable type value</span></span>

<span data-ttu-id="9d8b6-116">Use las propiedades de solo lectura siguientes para examinar una instancia de un tipo de valor que admite un valor NULL en busca de NULL y recuperar un valor de un tipo subyacente:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-116">Use the following readonly properties to examine an instance of a nullable value type for null and retrieve a value of an underlying type:</span></span>

- <span data-ttu-id="9d8b6-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica si una instancia de un tipo que acepta valores NULL tiene un valor de su tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>

- <span data-ttu-id="9d8b6-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> obtiene el valor de un tipo subyacente si <xref:System.Nullable%601.HasValue%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="9d8b6-119">Si <xref:System.Nullable%601.HasValue%2A> es `false`, la propiedad <xref:System.Nullable%601.Value%2A> inicia una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-119">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="9d8b6-120">En el código del ejemplo siguiente se usa la propiedad `HasValue` para comprobar si la variable contiene un valor antes de mostrarlo:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-120">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

<span data-ttu-id="9d8b6-121">También se puede comparar una variable de un tipo de valor que admite un valor NULL con `null` en lugar de usar la propiedad `HasValue`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-121">You also can compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="9d8b6-122">A partir de C# 7.0, se puede usar la [coincidencia de patrones](../../pattern-matching.md) tanto para examinar como para obtener un valor de un tipo de valor que admite un valor NULL:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-122">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable value type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="9d8b6-123">Conversión de un tipo de valor que admite un valor NULL a un tipo subyacente</span><span class="sxs-lookup"><span data-stu-id="9d8b6-123">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="9d8b6-124">Si es necesario asignar un valor de tipo de valor que admite un valor NULL a un tipo que no admite un valor NULL, use el [operador de uso combinado de NULL`??`](../../language-reference/operators/null-coalescing-operator.md) para especificar el valor que se va a asignar si un valor de tipo de valor que admite un valor NULL es NULL (también se puede usar el método <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>):</span><span class="sxs-lookup"><span data-stu-id="9d8b6-124">If you need to assign a value of a nullable value type to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a value of a nullable value type is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="9d8b6-125">Use el método <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> si el valor que se va usar cuando un valor de un tipo de valor que admite un valor NULL es `null` debe ser el valor predeterminado del tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-125">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a value of a nullable value type is `null` should be the default value of the underlying value type.</span></span>

<span data-ttu-id="9d8b6-126">Puede convertir de forma explícita un tipo de valor que admite un valor NULL en un tipo que no admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-126">You can explicitly cast a nullable value type to a non-nullable type.</span></span> <span data-ttu-id="9d8b6-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-127">For example:</span></span>

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="9d8b6-128">En tiempo de ejecución, si el valor de un tipo de valor que admite un valor NULL es `null`, la conversión explícita inicia una <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-128">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="9d8b6-129">Un tipo de valor que no acepta valores NULL se convierte implícitamente al tipo que acepta valores NULL correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-129">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>

## <a name="operators"></a><span data-ttu-id="9d8b6-130">Operadores</span><span class="sxs-lookup"><span data-stu-id="9d8b6-130">Operators</span></span>

<span data-ttu-id="9d8b6-131">Los tipos que aceptan valores NULL correspondientes también pueden hacer uso de los operadores predefinidos unario y binario, así como de cualquier operador definido por el usuario que exista para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-131">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by corresponding nullable types.</span></span> <span data-ttu-id="9d8b6-132">Estos operadores generan un valor `null` si uno o los dos operandos son `null`; de lo contrario, el operador usa los valores contenidos para calcular el resultado.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-132">These operators produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="9d8b6-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-133">For example:</span></span>

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="9d8b6-134">Para el tipo `bool?`, los operadores predefinidos `&` y `|` no siguen las reglas descritas en esta sección: el resultado de una evaluación de operador puede ser distinto de NULL incluso si uno de los operandos es `null`.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-134">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="9d8b6-135">Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](../../language-reference/operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="9d8b6-135">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="9d8b6-136">Para los operadores relacionales (`<`, `>`, `<=`, `>=`), si uno o ambos operandos son `null`, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-136">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are `null`, the result is `false`.</span></span> <span data-ttu-id="9d8b6-137">No asuma que, como una comparación determinada (por ejemplo, `<=`) devuelve `false`, la comparación contraria (`>`) devolverá `true`.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-137">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="9d8b6-138">En el ejemplo siguiente se muestra que 10 no es</span><span class="sxs-lookup"><span data-stu-id="9d8b6-138">The following example shows that 10 is</span></span>

- <span data-ttu-id="9d8b6-139">mayor o igual que `null`,</span><span class="sxs-lookup"><span data-stu-id="9d8b6-139">neither greater than or equal to `null`,</span></span>
- <span data-ttu-id="9d8b6-140">es menor que `null`.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-140">nor less than `null`.</span></span>

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

<span data-ttu-id="9d8b6-141">En el ejemplo anterior también se muestra que una comparación de igualdad entre dos tipos de valor que aceptan valores NULL donde ambos son NULL se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-141">The above example also shows that an equality comparison of two nullable value types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="9d8b6-142">Para más información, consulte la sección sobre [operadores de elevación](~/_csharplang/spec/expressions.md#lifted-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="9d8b6-142">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="9d8b6-143">Conversión boxing y conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="9d8b6-143">Boxing and unboxing</span></span>

<span data-ttu-id="9d8b6-144">A un tipo de valor que acepta valores NULL se le aplica la [conversión boxing](../types/boxing-and-unboxing.md) por las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-144">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="9d8b6-145">Si <xref:System.Nullable%601.HasValue%2A> devuelve `false`, se genera la referencia nula.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-145">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="9d8b6-146">Si <xref:System.Nullable%601.HasValue%2A> devuelve `true`, se aplica la conversión boxing a un valor del tipo de valor subyacente `T`, no a la instancia de <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="9d8b6-146">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="9d8b6-147">Se puede aplicar conversión unboxing al tipo de valor con conversión boxing al tipo que acepta valores NULL correspondiente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d8b6-147">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="9d8b6-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d8b6-148">See also</span></span>

- [<span data-ttu-id="9d8b6-149">Tipos de valores que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="9d8b6-149">Nullable value types</span></span>](index.md)
- [<span data-ttu-id="9d8b6-150">¿Qué significa exactamente "elevado"?</span><span class="sxs-lookup"><span data-stu-id="9d8b6-150">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
