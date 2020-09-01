---
description: 'Operador sizeof: Referencia de C#'
title: 'Operador sizeof: Referencia de C#'
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: f1358cbfb6cbc2942cef12e650f7bd362ba37a78
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136881"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="84629-103">Operador sizeof (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="84629-103">sizeof operator (C# reference)</span></span>

<span data-ttu-id="84629-104">El operador `sizeof` devuelve el número de bytes ocupados por una variable de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="84629-104">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="84629-105">El argumento del operador `sizeof` debe ser el nombre de un [tipo administrado](../builtin-types/unmanaged-types.md) o un parámetro de tipo que está [restringido](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) para ser un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="84629-105">The argument to the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="84629-106">El operador `sizeof` requiere un contexto de [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="84629-106">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="84629-107">Sin embargo, las expresiones presentadas en la tabla siguiente se evalúan en tiempo de compilación según los valores de constantes correspondientes y no necesitan un contexto de unsafe:</span><span class="sxs-lookup"><span data-stu-id="84629-107">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="84629-108">Expresión</span><span class="sxs-lookup"><span data-stu-id="84629-108">Expression</span></span>|<span data-ttu-id="84629-109">Valor constante</span><span class="sxs-lookup"><span data-stu-id="84629-109">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="84629-110">1</span><span class="sxs-lookup"><span data-stu-id="84629-110">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="84629-111">1</span><span class="sxs-lookup"><span data-stu-id="84629-111">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="84629-112">2</span><span class="sxs-lookup"><span data-stu-id="84629-112">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="84629-113">2</span><span class="sxs-lookup"><span data-stu-id="84629-113">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="84629-114">4</span><span class="sxs-lookup"><span data-stu-id="84629-114">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="84629-115">4</span><span class="sxs-lookup"><span data-stu-id="84629-115">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="84629-116">8</span><span class="sxs-lookup"><span data-stu-id="84629-116">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="84629-117">8</span><span class="sxs-lookup"><span data-stu-id="84629-117">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="84629-118">2</span><span class="sxs-lookup"><span data-stu-id="84629-118">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="84629-119">4</span><span class="sxs-lookup"><span data-stu-id="84629-119">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="84629-120">8</span><span class="sxs-lookup"><span data-stu-id="84629-120">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="84629-121">16</span><span class="sxs-lookup"><span data-stu-id="84629-121">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="84629-122">1</span><span class="sxs-lookup"><span data-stu-id="84629-122">1</span></span>|

<span data-ttu-id="84629-123">Tampoco es necesario usar un contexto de unsafe cuando el operando del operador `sizeof` es el nombre de un tipo [enum](../builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="84629-123">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../builtin-types/enum.md) type.</span></span>

<span data-ttu-id="84629-124">En el siguiente ejemplo se muestra el uso del operador `sizeof`:</span><span class="sxs-lookup"><span data-stu-id="84629-124">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](snippets/shared/SizeOfOperator.cs)]

<span data-ttu-id="84629-125">El operador `sizeof` devuelve un número de bytes que asignará Common Language Runtime en la memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="84629-125">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="84629-126">Para los tipos [struct](../builtin-types/struct.md), el valor incluye el relleno, tal y como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="84629-126">For [struct](../builtin-types/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="84629-127">El resultado del operador `sizeof` puede ser distinto del resultado del método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, que devuelve el tamaño de un tipo en la memoria *no administrada*.</span><span class="sxs-lookup"><span data-stu-id="84629-127">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="84629-128">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="84629-128">C# language specification</span></span>

<span data-ttu-id="84629-129">Para obtener más información, vea la sección [Operador sizeof](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="84629-129">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84629-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="84629-130">See also</span></span>

- [<span data-ttu-id="84629-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="84629-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="84629-132">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="84629-132">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="84629-133">Operadores relacionados con el puntero</span><span class="sxs-lookup"><span data-stu-id="84629-133">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="84629-134">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="84629-134">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="84629-135">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="84629-135">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="84629-136">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="84629-136">Generics in .NET</span></span>](../../../standard/generics/index.md)
