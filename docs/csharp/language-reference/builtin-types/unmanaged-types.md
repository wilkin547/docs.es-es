---
title: Tipos no administrados - Referencia de C#
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 9dd2ab4e044b8a86bfe72a6fcf2481b8e1e80bf4
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507235"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="49c28-102">Tipos no administrados (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="49c28-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="49c28-103">Un tipo es un **tipo no administrado** si es cualquiera de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="49c28-103">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="49c28-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`</span><span class="sxs-lookup"><span data-stu-id="49c28-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="49c28-105">Cualquier tipo [enum](enum.md).</span><span class="sxs-lookup"><span data-stu-id="49c28-105">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="49c28-106">Cualquier tipo [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="49c28-106">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="49c28-107">Cualquier tipo de [struct](struct.md) definido por el usuario que solo contenga campos de tipos no administrados, en C# 7.3 y versiones anteriores, no es un tipo construido (un tipo que incluya al menos un argumento de tipo)</span><span class="sxs-lookup"><span data-stu-id="49c28-107">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="49c28-108">A partir de C# 7.3, puede usar [`unmanaged`constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) para especificar que un parámetro de tipo es un tipo no administrado que no acepta valores NULL y que no es de puntero.</span><span class="sxs-lookup"><span data-stu-id="49c28-108">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="49c28-109">A partir C# 8.0, un tipo de struct *construido* que solo contenga campos de tipos no administrados también es no administrado, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49c28-109">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](snippets/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="49c28-110">Un struct genérico puede ser el origen de los tipos no administrados y de los tipos construidos no administrados.</span><span class="sxs-lookup"><span data-stu-id="49c28-110">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="49c28-111">En el ejemplo anterior se define un struct `Coords<T>` genérico y se presentan los ejemplos de tipos construidos no administrados.</span><span class="sxs-lookup"><span data-stu-id="49c28-111">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="49c28-112">El ejemplo de un tipo no administrado es `Coords<object>`.</span><span class="sxs-lookup"><span data-stu-id="49c28-112">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="49c28-113">No está administrado porque tiene los campos del tipo `object`, que es no administrado.</span><span class="sxs-lookup"><span data-stu-id="49c28-113">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="49c28-114">Si desea que *todos* los tipos construidos sean tipos no administrados, use la restricción `unmanaged` en la definición de un struct genérico:</span><span class="sxs-lookup"><span data-stu-id="49c28-114">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](snippets/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="49c28-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="49c28-115">C# language specification</span></span>

<span data-ttu-id="49c28-116">Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="49c28-116">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49c28-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="49c28-117">See also</span></span>

- [<span data-ttu-id="49c28-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="49c28-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="49c28-119">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="49c28-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="49c28-120">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="49c28-120">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="49c28-121">sizeof (operador)</span><span class="sxs-lookup"><span data-stu-id="49c28-121">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="49c28-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="49c28-122">stackalloc</span></span>](../operators/stackalloc.md)
