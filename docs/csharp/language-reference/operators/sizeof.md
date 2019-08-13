---
title: 'Operador sizeof: Referencia de C#'
ms.custom: seodec18
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: c455804923f4d0e7cc8f556bb9b9df34b6332d82
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796517"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="43867-102">Operador sizeof (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="43867-102">sizeof operator (C# reference)</span></span>

<span data-ttu-id="43867-103">El operador `sizeof` devuelve el número de bytes ocupados por una variable de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="43867-103">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="43867-104">El argumento del operador `sizeof` debe ser el nombre de un [tipo administrado](../builtin-types/unmanaged-types.md) o un parámetro de tipo que está [restringido](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) para ser un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="43867-104">The argument to the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="43867-105">El operador `sizeof` requiere un contexto de [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="43867-105">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="43867-106">Sin embargo, las expresiones presentadas en la tabla siguiente se evalúan en tiempo de compilación según los valores de constantes correspondientes y no necesitan un contexto de unsafe:</span><span class="sxs-lookup"><span data-stu-id="43867-106">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="43867-107">Expresión</span><span class="sxs-lookup"><span data-stu-id="43867-107">Expression</span></span>|<span data-ttu-id="43867-108">Valor constante</span><span class="sxs-lookup"><span data-stu-id="43867-108">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="43867-109">1</span><span class="sxs-lookup"><span data-stu-id="43867-109">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="43867-110">1</span><span class="sxs-lookup"><span data-stu-id="43867-110">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="43867-111">2</span><span class="sxs-lookup"><span data-stu-id="43867-111">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="43867-112">2</span><span class="sxs-lookup"><span data-stu-id="43867-112">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="43867-113">4</span><span class="sxs-lookup"><span data-stu-id="43867-113">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="43867-114">4</span><span class="sxs-lookup"><span data-stu-id="43867-114">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="43867-115">8</span><span class="sxs-lookup"><span data-stu-id="43867-115">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="43867-116">8</span><span class="sxs-lookup"><span data-stu-id="43867-116">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="43867-117">2</span><span class="sxs-lookup"><span data-stu-id="43867-117">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="43867-118">4</span><span class="sxs-lookup"><span data-stu-id="43867-118">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="43867-119">8</span><span class="sxs-lookup"><span data-stu-id="43867-119">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="43867-120">16</span><span class="sxs-lookup"><span data-stu-id="43867-120">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="43867-121">1</span><span class="sxs-lookup"><span data-stu-id="43867-121">1</span></span>|

<span data-ttu-id="43867-122">Tampoco es necesario usar un contexto de unsafe cuando el operando del operador `sizeof` es el nombre de un tipo [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="43867-122">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="43867-123">En el siguiente ejemplo se muestra el uso del operador `sizeof`:</span><span class="sxs-lookup"><span data-stu-id="43867-123">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

<span data-ttu-id="43867-124">El operador `sizeof` devuelve un número de bytes que asignará Common Language Runtime en la memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="43867-124">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="43867-125">Para los tipos [struct](../keywords/struct.md), el valor incluye el relleno, tal y como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="43867-125">For [struct](../keywords/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="43867-126">El resultado del operador `sizeof` puede ser distinto del resultado del método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, que devuelve el tamaño de un tipo en la memoria *no administrada*.</span><span class="sxs-lookup"><span data-stu-id="43867-126">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="43867-127">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="43867-127">C# language specification</span></span>

<span data-ttu-id="43867-128">Para obtener más información, vea la sección [Operador sizeof](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="43867-128">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="43867-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="43867-129">See also</span></span>

- [<span data-ttu-id="43867-130">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="43867-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="43867-131">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="43867-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="43867-132">Operadores relacionados con el puntero</span><span class="sxs-lookup"><span data-stu-id="43867-132">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="43867-133">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="43867-133">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="43867-134">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="43867-134">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
