---
title: Uso de tipos que aceptan valores NULL - Guía de programación de C#
ms.custom: seodec18
description: Obtenga información sobre cómo trabajar con tipos de C# que aceptan valores NULL
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 75b8889f5f1f1b0dab4aa365daa34ef5ae226b02
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588832"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="8d749-103">Uso de tipos que aceptan valores NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8d749-103">Using nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="8d749-104">Los tipos que aceptan valores NULL son los que representan todos los valores de un tipo de valor `T` subyacente y un valor [NULL](../../language-reference/keywords/null.md) adicional.</span><span class="sxs-lookup"><span data-stu-id="8d749-104">Nullable types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="8d749-105">Para obtener más información, vea el tema [Tipos que aceptan valores NULL](index.md).</span><span class="sxs-lookup"><span data-stu-id="8d749-105">For more information, see the [Nullable types](index.md) topic.</span></span>

<span data-ttu-id="8d749-106">Puede hacer referencia a un tipo que acepta valores NULL en cualquiera de las formas siguientes: `Nullable<T>` o `T?`.</span><span class="sxs-lookup"><span data-stu-id="8d749-106">You can refer to a nullable type in any of the following forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="8d749-107">Estas dos formas son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="8d749-107">These two forms are interchangeable.</span></span>  
  
## <a name="declaration-and-assignment"></a><span data-ttu-id="8d749-108">Declaración y asignación</span><span class="sxs-lookup"><span data-stu-id="8d749-108">Declaration and assignment</span></span>

<span data-ttu-id="8d749-109">Como un tipo de valor se puede convertir de forma implícita al tipo que acepta valores NULL correspondiente, un valor se asigna a un tipo que acepta valores NULL como se haría para su tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="8d749-109">As a value type can be implicitly converted to the corresponding nullable type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="8d749-110">También se puede asignar el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="8d749-110">You also can assign the `null` value.</span></span>  <span data-ttu-id="8d749-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8d749-111">For example:</span></span>
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="8d749-112">Examen de un valor de tipo que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="8d749-112">Examination of a nullable type value</span></span>

<span data-ttu-id="8d749-113">Use las propiedades de solo lectura siguientes para examinar una instancia de un tipo que acepta valores NULL en busca de NULL y recuperar un valor de un tipo subyacente:</span><span class="sxs-lookup"><span data-stu-id="8d749-113">Use the following readonly properties to examine an instance of a nullable type for null and retrieve a value of an underlying type:</span></span>  
  
- <span data-ttu-id="8d749-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica si una instancia de un tipo que acepta valores NULL tiene un valor de su tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="8d749-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>
  
- <span data-ttu-id="8d749-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> obtiene el valor de un tipo subyacente si <xref:System.Nullable%601.HasValue%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="8d749-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="8d749-116">Si <xref:System.Nullable%601.HasValue%2A> es `false`, la propiedad <xref:System.Nullable%601.Value%2A> inicia una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="8d749-116">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>
  
<span data-ttu-id="8d749-117">En el código del ejemplo siguiente se usa la propiedad `HasValue` para comprobar si la variable contiene un valor antes de mostrarlo:</span><span class="sxs-lookup"><span data-stu-id="8d749-117">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
<span data-ttu-id="8d749-118">También se puede comparar una variable de tipo que acepta valores NULL con `null` en lugar de usar la propiedad `HasValue`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d749-118">You also can compare a nullable type variable with `null` instead of using the `HasValue` property, as the following example shows:</span></span>  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="8d749-119">A partir de C# 7.0, se puede usar la [coincidencia de patrones](../../pattern-matching.md) tanto para examinar como para obtener un valor de un tipo que acepta valores NULL:</span><span class="sxs-lookup"><span data-stu-id="8d749-119">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a><span data-ttu-id="8d749-120">Conversión de un tipo que acepta valores NULL a un tipo subyacente</span><span class="sxs-lookup"><span data-stu-id="8d749-120">Conversion from a nullable type to an underlying type</span></span>

<span data-ttu-id="8d749-121">Si es necesario asignar un valor de tipo que acepta valores NULL a un tipo que no acepta valores NULL, use el [operador de uso combinado de NULL`??`](../../language-reference/operators/null-coalescing-operator.md) para especificar el valor que se va a asignar si un valor de tipo que acepta valores NULL es NULL (también se puede usar el método <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>):</span><span class="sxs-lookup"><span data-stu-id="8d749-121">If you need to assign a nullable type value to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a nullable type value is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="8d749-122">Use el método <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> si el valor que se va usar cuando un valor de tipo que acepta valores NULL es NULL debe ser el valor predeterminado del tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="8d749-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is null should be the default value of the underlying value type.</span></span>
  
<span data-ttu-id="8d749-123">Puede convertir de forma explícita un tipo que acepta valores NULL en un tipo que no acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="8d749-123">You can explicitly cast a nullable type to a non-nullable type.</span></span> <span data-ttu-id="8d749-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8d749-124">For example:</span></span>  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="8d749-125">En tiempo de ejecución, si el valor de un tipo que acepta valores NULL es NULL, la conversión explícita inicia una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="8d749-125">At run time, if the value of a nullable type is null, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="8d749-126">Un tipo de valor que no acepta valores NULL se convierte implícitamente al tipo que acepta valores NULL correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8d749-126">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>
  
## <a name="operators"></a><span data-ttu-id="8d749-127">Operadores</span><span class="sxs-lookup"><span data-stu-id="8d749-127">Operators</span></span>

<span data-ttu-id="8d749-128">Los tipos que aceptan valores NULL también pueden hacer uso de los operadores predefinidos unario y binario, así como de cualquier operador definido por el usuario que exista para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="8d749-128">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="8d749-129">Estos operadores generan un valor NULL si uno o los dos operandos son NULL; si no, el operador usa los valores contenidos para calcular el resultado.</span><span class="sxs-lookup"><span data-stu-id="8d749-129">These operators produce a null value if one or both operands are null; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="8d749-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8d749-130">For example:</span></span>  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="8d749-131">Para el tipo `bool?`, los operadores predefinidos `&` y `|` no siguen las regas descritas en esta sección: el resultado de una evaluación de operador puede ser distinto de NULL incluso si uno de los operandos es NULL.</span><span class="sxs-lookup"><span data-stu-id="8d749-131">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is null.</span></span> <span data-ttu-id="8d749-132">Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](../../language-reference/operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="8d749-132">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="8d749-133">Para los operadores relacionales (`<`, `>`, `<=`, `>=`), si uno o ambos operandos son NULL, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="8d749-133">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are null, the result is `false`.</span></span> <span data-ttu-id="8d749-134">No asuma que, como una comparación determinada (por ejemplo, `<=`) devuelve `false`, la comparación contraria (`>`) devolverá `true`.</span><span class="sxs-lookup"><span data-stu-id="8d749-134">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="8d749-135">En el ejemplo siguiente se muestra que 10 no es</span><span class="sxs-lookup"><span data-stu-id="8d749-135">The following example shows that 10 is</span></span>

- <span data-ttu-id="8d749-136">mayor o igual que NULL,</span><span class="sxs-lookup"><span data-stu-id="8d749-136">neither greater than or equal to null,</span></span>
- <span data-ttu-id="8d749-137">ni menor que NULL.</span><span class="sxs-lookup"><span data-stu-id="8d749-137">nor less than null.</span></span>
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
<span data-ttu-id="8d749-138">En el ejemplo anterior también se muestra que una comparación de igualdad entre dos tipos que aceptan valores NULL donde ambos son NULL se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="8d749-138">The above example also shows that an equality comparison of two nullable types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="8d749-139">Para más información, consulte la sección sobre [operadores de elevación](~/_csharplang/spec/expressions.md#lifted-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8d749-139">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="8d749-140">Conversión boxing y conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="8d749-140">Boxing and unboxing</span></span>

<span data-ttu-id="8d749-141">A un tipo de valor que acepta valores NULL se le aplica la [conversión boxing](../types/boxing-and-unboxing.md) por las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d749-141">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="8d749-142">Si <xref:System.Nullable%601.HasValue%2A> devuelve `false`, se genera la referencia nula.</span><span class="sxs-lookup"><span data-stu-id="8d749-142">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>  
- <span data-ttu-id="8d749-143">Si <xref:System.Nullable%601.HasValue%2A> devuelve `true`, se aplica la conversión boxing a un valor del tipo de valor subyacente `T`, no a la instancia de <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="8d749-143">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="8d749-144">Se puede aplicar conversión unboxing al tipo de valor con conversión boxing al tipo que acepta valores NULL correspondiente, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d749-144">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="8d749-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d749-145">See also</span></span>

- <span data-ttu-id="8d749-146">[Nullable types](index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="8d749-146">[Nullable types](index.md)</span></span>
- [<span data-ttu-id="8d749-147">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8d749-147">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8d749-148">¿Qué significa exactamente "elevado"?</span><span class="sxs-lookup"><span data-stu-id="8d749-148">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
