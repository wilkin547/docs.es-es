---
title: Operadores bit a bit (F#)
description: 'Obtenga información acerca de los operadores bit a bit que están disponibles en el lenguaje de programación de F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4d5abff564a5d1dcbe52b99edf431ca10e442061
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="bitwise-operators"></a><span data-ttu-id="bbb8a-103">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="bbb8a-103">Bitwise Operators</span></span>

<span data-ttu-id="bbb8a-104">En este tema se describe los operadores bit a bit que están disponibles en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-104">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="bbb8a-105">Resumen de operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="bbb8a-105">Summary of Bitwise Operators</span></span>
<span data-ttu-id="bbb8a-106">En la tabla siguiente describe los operadores bit a bit que se admiten para los tipos enteros con conversión unboxing en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-106">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="bbb8a-107">Operador</span><span class="sxs-lookup"><span data-stu-id="bbb8a-107">Operator</span></span>|<span data-ttu-id="bbb8a-108">Notas</span><span class="sxs-lookup"><span data-stu-id="bbb8a-108">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="bbb8a-109">Operador AND bit a bit.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-109">Bitwise AND operator.</span></span> <span data-ttu-id="bbb8a-110">Bits del resultado tienen el valor 1 si y solo si los bits correspondientes en ambos operandos de origen son 1.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-110">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="bbb8a-111">Operador OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-111">Bitwise OR operator.</span></span> <span data-ttu-id="bbb8a-112">Bits del resultado tienen el valor 1 si el valor de los bits correspondientes en el origen de los operandos son 1.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-112">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="bbb8a-113">Bit a bit operador OR exclusivo.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-113">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="bbb8a-114">Bits del resultado tienen el valor 1 si y solo si los bits en los operandos de origen tienen valores distintos.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-114">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="bbb8a-115">Operador de negación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-115">Bitwise negation operator.</span></span> <span data-ttu-id="bbb8a-116">Esto es un operador unario y genera un resultado en el que todos los bits 0 del operando de origen se convierten en bits 1 y todos los bits 1 se convierten en bits 0.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-116">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="bbb8a-117">Bit a bit el operador de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-117">Bitwise left-shift operator.</span></span> <span data-ttu-id="bbb8a-118">El resultado es que el primer operando con bits desplazado a la izquierda el número de bits del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-118">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="bbb8a-119">Bits desplazados fuera de la posición más importante no se pasan a la posición menos significativa.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-119">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="bbb8a-120">Los bits menos significativos se rellenan con ceros.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-120">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="bbb8a-121">El tipo del segundo argumento es `int32`.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-121">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="bbb8a-122">Bit a bit el operador de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-122">Bitwise right-shift operator.</span></span> <span data-ttu-id="bbb8a-123">El resultado es el primer operando con los bits que se desplazan a la derecha el número de bits del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-123">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="bbb8a-124">Los bits desplazados fuera de la posición menos significativa no se pasan en la posición más significativa.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-124">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="bbb8a-125">Para los tipos sin signo, los bits más significativos se rellenan con ceros.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-125">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="bbb8a-126">Para los tipos con signo, los bits más significativos se rellenan con los.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-126">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="bbb8a-127">El tipo del segundo argumento es `int32`.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-127">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="bbb8a-128">Los tipos siguientes se pueden utilizar con operadores bit a bit: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, y `unativeint`.</span><span class="sxs-lookup"><span data-stu-id="bbb8a-128">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbb8a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbb8a-129">See Also</span></span>
[<span data-ttu-id="bbb8a-130">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="bbb8a-130">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="bbb8a-131">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="bbb8a-131">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="bbb8a-132">Operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="bbb8a-132">Boolean Operators</span></span>](boolean-operators.md)

