---
title: Enumeraciones (F#)
description: 'Obtenga información sobre cómo usar las enumeraciones de F # en lugar de literales para hacer que el código más legible y fácil de mantener.'
ms.date: 05/16/2016
ms.openlocfilehash: 47fb353c2698f8b1474834ebbd1b0eff2c7f76e7
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44097092"
---
# <a name="enumerations"></a><span data-ttu-id="2879a-103">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="2879a-103">Enumerations</span></span>

<span data-ttu-id="2879a-104">*Enumeraciones*, también conocida como *enumeraciones*,, son tipos enteros donde las etiquetas se asignan a un subconjunto de los valores.</span><span class="sxs-lookup"><span data-stu-id="2879a-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="2879a-105">Se pueden usar en lugar de los literales para que el código sea más fácil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="2879a-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="2879a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2879a-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="2879a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2879a-107">Remarks</span></span>

<span data-ttu-id="2879a-108">Una enumeración se parece mucho a una unión discriminada que tiene valores simples, salvo que se pueden especificar los valores.</span><span class="sxs-lookup"><span data-stu-id="2879a-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="2879a-109">Normalmente, los valores son enteros que comienzan en 0 o 1 o enteros que representan las posiciones de bits.</span><span class="sxs-lookup"><span data-stu-id="2879a-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="2879a-110">Si una enumeración está pensada para representar las posiciones de bits, también se debe utilizar el [marcas](xref:System.FlagsAttribute) atributo.</span><span class="sxs-lookup"><span data-stu-id="2879a-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="2879a-111">El tipo subyacente de la enumeración se determina a partir del literal que se usa, por lo que, por ejemplo, puede usar literales con sufijo, como `1u`, `2u`, y así sucesivamente, para un entero sin signo (`uint32`) tipo.</span><span class="sxs-lookup"><span data-stu-id="2879a-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="2879a-112">Cuando se hace referencia a los valores con nombre, debe usar el nombre del propio tipo de enumeración como un calificador, es decir, `enum-name.value1`, no sólo `value1`.</span><span class="sxs-lookup"><span data-stu-id="2879a-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="2879a-113">Este comportamiento difiere de las uniones discriminadas.</span><span class="sxs-lookup"><span data-stu-id="2879a-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="2879a-114">Esto es porque las enumeraciones siempre tienen la [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) atributo.</span><span class="sxs-lookup"><span data-stu-id="2879a-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="2879a-115">El código siguiente muestra la declaración y el uso de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="2879a-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="2879a-116">Puede convertir fácilmente las enumeraciones con el tipo subyacente mediante el operador adecuado, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2879a-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="2879a-117">Los tipos enumerados pueden tener uno de los siguientes tipos subyacentes: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, y `char`.</span><span class="sxs-lookup"><span data-stu-id="2879a-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="2879a-118">Tipos de enumeración se representan en .NET Framework como tipos que se heredan de `System.Enum`, que a su vez se hereda de `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="2879a-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="2879a-119">Por lo tanto, son tipos de valor que se encuentran en la pila o en línea en el objeto contenedor, y cualquier valor del tipo subyacente es un valor válido de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2879a-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="2879a-120">Esto es importante cuando los valores de coincidencia de patrones en la enumeración, ya que hay que proporcionar un patrón que detecta los valores sin nombre.</span><span class="sxs-lookup"><span data-stu-id="2879a-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="2879a-121">El `enum` función de la biblioteca de F # puede usarse para generar un valor de enumeración, incluso un valor distinto de uno de los predefinidos, valores con nombre.</span><span class="sxs-lookup"><span data-stu-id="2879a-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="2879a-122">Usa el `enum` funcione como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="2879a-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="2879a-123">El valor predeterminado `enum` función funciona con el tipo `int32`.</span><span class="sxs-lookup"><span data-stu-id="2879a-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="2879a-124">Por lo tanto, no se puede usar con tipos de enumeración que tienen otros tipos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="2879a-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="2879a-125">En su lugar, use lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2879a-125">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="2879a-126">Además, los casos, para las enumeraciones siempre se emiten como `public`.</span><span class="sxs-lookup"><span data-stu-id="2879a-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="2879a-127">Esto es para que se alineen con C# y el resto de la plataforma. NET.</span><span class="sxs-lookup"><span data-stu-id="2879a-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="2879a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2879a-128">See also</span></span>

- [<span data-ttu-id="2879a-129">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="2879a-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2879a-130">Conversiones</span><span class="sxs-lookup"><span data-stu-id="2879a-130">Casting and Conversions</span></span>](casting-and-conversions.md)
