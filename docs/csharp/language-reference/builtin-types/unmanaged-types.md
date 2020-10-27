---
description: Obtenga información sobre los tipos no administrados en C#.
title: Tipos no administrados - Referencia de C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 4374872af13c94e1a1af6b9f2c431f076c6f7dff
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471804"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="e2056-103">Tipos no administrados (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e2056-103">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="e2056-104">Un tipo es un **tipo no administrado** si es cualquiera de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="e2056-104">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="e2056-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`</span><span class="sxs-lookup"><span data-stu-id="e2056-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="e2056-106">Cualquier tipo [enum](enum.md).</span><span class="sxs-lookup"><span data-stu-id="e2056-106">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="e2056-107">Cualquier tipo [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="e2056-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="e2056-108">Cualquier tipo de [struct](struct.md) definido por el usuario que solo contenga campos de tipos no administrados, en C# 7.3 y versiones anteriores, no es un tipo construido (un tipo que incluya al menos un argumento de tipo)</span><span class="sxs-lookup"><span data-stu-id="e2056-108">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="e2056-109">A partir de C# 7.3, puede usar [`unmanaged`constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) para especificar que un parámetro de tipo es un tipo no administrado que no acepta valores NULL y que no es de puntero.</span><span class="sxs-lookup"><span data-stu-id="e2056-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="e2056-110">A partir C# 8.0, un tipo de struct *construido* que solo contenga campos de tipos no administrados también es no administrado, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2056-110">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](snippets/shared/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="e2056-111">Un struct genérico puede ser el origen de los tipos no administrados y de los tipos construidos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e2056-111">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="e2056-112">En el ejemplo anterior se define un struct `Coords<T>` genérico y se presentan los ejemplos de tipos construidos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e2056-112">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="e2056-113">El ejemplo de un tipo no administrado es `Coords<object>`.</span><span class="sxs-lookup"><span data-stu-id="e2056-113">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="e2056-114">No está administrado porque tiene los campos del tipo `object`, que es no administrado.</span><span class="sxs-lookup"><span data-stu-id="e2056-114">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="e2056-115">Si desea que *todos* los tipos construidos sean tipos no administrados, use la restricción `unmanaged` en la definición de un struct genérico:</span><span class="sxs-lookup"><span data-stu-id="e2056-115">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](snippets/shared/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="e2056-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="e2056-116">C# language specification</span></span>

<span data-ttu-id="e2056-117">Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e2056-117">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2056-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2056-118">See also</span></span>

- [<span data-ttu-id="e2056-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e2056-119">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e2056-120">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="e2056-120">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="e2056-121">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="e2056-121">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="e2056-122">sizeof (operador)</span><span class="sxs-lookup"><span data-stu-id="e2056-122">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="e2056-123">stackalloc</span><span class="sxs-lookup"><span data-stu-id="e2056-123">stackalloc</span></span>](../operators/stackalloc.md)
