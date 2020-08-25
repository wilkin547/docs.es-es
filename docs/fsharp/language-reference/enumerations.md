---
title: Enumeraciones
description: 'Obtenga información sobre cómo usar las enumeraciones de F # en lugar de literales para que el código sea más legible y fácil de mantener.'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812112"
---
# <a name="enumerations"></a><span data-ttu-id="50f4b-103">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="50f4b-103">Enumerations</span></span>

<span data-ttu-id="50f4b-104">Las *enumeraciones*, también conocidas como *enumeraciones*,, son tipos enteros donde las etiquetas se asignan a un subconjunto de los valores.</span><span class="sxs-lookup"><span data-stu-id="50f4b-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="50f4b-105">Se pueden usar en lugar de los literales para que el código sea más fácil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="50f4b-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="50f4b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50f4b-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="50f4b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50f4b-107">Remarks</span></span>

<span data-ttu-id="50f4b-108">Una enumeración es muy similar a una Unión discriminada que tiene valores simples, con la excepción de que se pueden especificar los valores.</span><span class="sxs-lookup"><span data-stu-id="50f4b-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="50f4b-109">Los valores suelen ser enteros que comienzan en 0 o 1, o enteros que representan posiciones de bits.</span><span class="sxs-lookup"><span data-stu-id="50f4b-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="50f4b-110">Si una enumeración está pensada para representar posiciones de bits, debe usar también el atributo [Flags](xref:System.FlagsAttribute) .</span><span class="sxs-lookup"><span data-stu-id="50f4b-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="50f4b-111">El tipo subyacente de la enumeración se determina a partir del literal que se utiliza, de modo que, por ejemplo, puede usar literales con un sufijo, como `1u` , `2u` , etc., para un tipo entero () sin signo `uint32` .</span><span class="sxs-lookup"><span data-stu-id="50f4b-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="50f4b-112">Cuando se hace referencia a los valores con nombre, debe usar el nombre del tipo de enumeración como calificador, es decir, `enum-name.value1` , no solo `value1` .</span><span class="sxs-lookup"><span data-stu-id="50f4b-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="50f4b-113">Este comportamiento difiere del de las uniones discriminadas.</span><span class="sxs-lookup"><span data-stu-id="50f4b-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="50f4b-114">Esto se debe a que las enumeraciones siempre tienen el atributo [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) .</span><span class="sxs-lookup"><span data-stu-id="50f4b-114">This is because enumerations always have the [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) attribute.</span></span>

<span data-ttu-id="50f4b-115">En el código siguiente se muestra la declaración y el uso de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="50f4b-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="50f4b-116">Puede convertir fácilmente las enumeraciones en el tipo subyacente mediante el operador adecuado, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="50f4b-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="50f4b-117">Los tipos enumerados pueden tener uno de los siguientes tipos subyacentes: `sbyte` , `byte` , `int16` , `uint16` , `int32` , `uint32` , `int64` ,, `uint16` `uint64` y `char` .</span><span class="sxs-lookup"><span data-stu-id="50f4b-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="50f4b-118">Los tipos de enumeración se representan en el .NET Framework como tipos que se heredan de `System.Enum` , que a su vez se hereda de `System.ValueType` .</span><span class="sxs-lookup"><span data-stu-id="50f4b-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="50f4b-119">Por lo tanto, son tipos de valor que se encuentran en la pila o insertados en el objeto contenedor, y cualquier valor del tipo subyacente es un valor válido de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="50f4b-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="50f4b-120">Esto es importante cuando la coincidencia de patrones en los valores de enumeración, porque tiene que proporcionar un patrón que detecte los valores sin nombre.</span><span class="sxs-lookup"><span data-stu-id="50f4b-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="50f4b-121">La `enum` función de la biblioteca de F # se puede usar para generar un valor de enumeración, incluso un valor distinto de uno de los valores con nombre predefinidos.</span><span class="sxs-lookup"><span data-stu-id="50f4b-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="50f4b-122">La función se usa `enum` como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="50f4b-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="50f4b-123">La `enum` función predeterminada funciona con el tipo `int32` .</span><span class="sxs-lookup"><span data-stu-id="50f4b-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="50f4b-124">Por lo tanto, no se puede utilizar con tipos de enumeración que tienen otros tipos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="50f4b-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="50f4b-125">En su lugar, use lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="50f4b-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="50f4b-126">Además, los casos de enumeración siempre se emiten como `public` .</span><span class="sxs-lookup"><span data-stu-id="50f4b-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="50f4b-127">Esto es para que se alineen con C# y el resto de la plataforma .NET.</span><span class="sxs-lookup"><span data-stu-id="50f4b-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="50f4b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="50f4b-128">See also</span></span>

- [<span data-ttu-id="50f4b-129">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="50f4b-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="50f4b-130">Conversiones</span><span class="sxs-lookup"><span data-stu-id="50f4b-130">Casting and Conversions</span></span>](casting-and-conversions.md)
