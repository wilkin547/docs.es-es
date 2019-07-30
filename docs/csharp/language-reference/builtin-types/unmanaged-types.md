---
title: Tipos no administrados - Referencia de C#
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512075"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="feddd-102">Tipos no administrados (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="feddd-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="feddd-103">Un **tipo no administrado** es todo aquel que no es un tipo de referencia ni un tipo construido (un tipo que incluye al menos un argumento de tipo) y que no contiene ningún campo de tipo de referencia ni de tipo construido en ningún nivel del anidamiento.</span><span class="sxs-lookup"><span data-stu-id="feddd-103">An **unmanaged type** is any type that isn't a reference type or constructed type (a type that includes at least one type argument), and doesn't contain reference type or constructed type fields at any level of nesting.</span></span> <span data-ttu-id="feddd-104">En otras palabras, un tipo no administrado es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="feddd-104">In other words, an unmanaged type is one of the following:</span></span>

- <span data-ttu-id="feddd-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` o `bool`</span><span class="sxs-lookup"><span data-stu-id="feddd-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="feddd-106">Cualquier tipo [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="feddd-106">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="feddd-107">Cualquier tipo [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="feddd-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="feddd-108">Cualquier tipo [struct](../keywords/struct.md) definido por el usuario que no sea un tipo construido y que contenga campos solo de tipos no administrados.</span><span class="sxs-lookup"><span data-stu-id="feddd-108">Any user-defined [struct](../keywords/struct.md) type that is not a constructed type and contains fields of unmanaged types only</span></span>

<span data-ttu-id="feddd-109">A partir de C# 7.3, puede usar [`unmanaged`constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) para especificar que un parámetro de tipo es un tipo no administrado que no es de puntero.</span><span class="sxs-lookup"><span data-stu-id="feddd-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer unmanaged type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="feddd-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="feddd-110">C# language specification</span></span>

<span data-ttu-id="feddd-111">Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="feddd-111">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="feddd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="feddd-112">See also</span></span>

- [<span data-ttu-id="feddd-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="feddd-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="feddd-114">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="feddd-114">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="feddd-115">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="feddd-115">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="feddd-116">sizeof (operador)</span><span class="sxs-lookup"><span data-stu-id="feddd-116">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="feddd-117">stackalloc (operador)</span><span class="sxs-lookup"><span data-stu-id="feddd-117">stackalloc operator</span></span>](../operators/stackalloc.md)
