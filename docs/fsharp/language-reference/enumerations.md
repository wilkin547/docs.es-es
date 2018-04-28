---
title: Enumeraciones (F#)
description: 'Obtenga información acerca de cómo usar las enumeraciones de F # en lugar de literales para que el código más legible y fácil de mantener.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4b1a61fb69403f826733893667e55991d39867c6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="enumerations"></a><span data-ttu-id="21586-103">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="21586-103">Enumerations</span></span>

<span data-ttu-id="21586-104">*Enumeraciones*, también conocida como *enumeraciones*, son tipos integrales donde las etiquetas están asignadas a un subconjunto de los valores.</span><span class="sxs-lookup"><span data-stu-id="21586-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="21586-105">Se pueden usar en lugar de los literales para que el código sea más fácil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="21586-105">You can use them in place of literals to make code more readable and maintainable.</span></span>


## <a name="syntax"></a><span data-ttu-id="21586-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21586-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="21586-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21586-107">Remarks</span></span>
<span data-ttu-id="21586-108">Una enumeración se parece mucho a una unión discriminada con valores simples, salvo que se pueden especificar los valores.</span><span class="sxs-lookup"><span data-stu-id="21586-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="21586-109">Los valores son normalmente enteros que representan las posiciones de bits o enteros que empiezan en 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="21586-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="21586-110">Si una enumeración está pensada para representar posiciones de bits, también debe usar el [marcas](xref:System.FlagsAttribute) atributo.</span><span class="sxs-lookup"><span data-stu-id="21586-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="21586-111">El tipo subyacente de la enumeración se determina a partir del valor literal que se usa, por lo que, por ejemplo, puede usar literales con sufijo, como `1u`, `2u`, y así sucesivamente, para un entero sin signo (`uint32`) tipo.</span><span class="sxs-lookup"><span data-stu-id="21586-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="21586-112">Cuando se hace referencia a los valores con nombre, debe utilizar el nombre del propio tipo de enumeración como calificador, es decir, `enum-name.value1`, no sólo `value1`.</span><span class="sxs-lookup"><span data-stu-id="21586-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="21586-113">Este comportamiento difiere del de las uniones discriminadas.</span><span class="sxs-lookup"><span data-stu-id="21586-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="21586-114">Esto es porque las enumeraciones siempre tienen la [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) atributo.</span><span class="sxs-lookup"><span data-stu-id="21586-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="21586-115">El código siguiente muestra la declaración y el uso de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="21586-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="21586-116">Fácilmente puede convertir enumeraciones en el tipo subyacente mediante el operador adecuado, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="21586-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="21586-117">Los tipos enumerados pueden tener uno de los tipos subyacentes siguientes: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, y `char`.</span><span class="sxs-lookup"><span data-stu-id="21586-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="21586-118">Tipos de enumeración se representan en .NET Framework como tipos que se heredan de `System.Enum`, que a su vez se hereda de `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="21586-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="21586-119">Por lo tanto, son tipos de valores que se encuentran en la pila o en línea en el objeto contenedor, y cualquier valor del tipo subyacente es un valor válido de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="21586-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="21586-120">Esto es importante cuando los valores de coincidencia de patrones en la enumeración, ya que tendrá que proporcionar un patrón que detecta los valores sin nombre.</span><span class="sxs-lookup"><span data-stu-id="21586-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="21586-121">El `enum` función en la biblioteca de F # puede utilizarse para generar un valor de enumeración, incluso un valor distinto de predefinido, valores con nombre.</span><span class="sxs-lookup"><span data-stu-id="21586-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="21586-122">Usa el `enum` funcione como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="21586-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="21586-123">El valor predeterminado `enum` función funciona con el tipo de `int32`.</span><span class="sxs-lookup"><span data-stu-id="21586-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="21586-124">Por lo tanto, no puede usarse con tipos de enumeración que tienen otros tipos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="21586-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="21586-125">En su lugar, utilice el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="21586-125">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a><span data-ttu-id="21586-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="21586-126">See Also</span></span>
[<span data-ttu-id="21586-127">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="21586-127">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="21586-128">Conversiones</span><span class="sxs-lookup"><span data-stu-id="21586-128">Casting and Conversions</span></span>](casting-and-conversions.md)
