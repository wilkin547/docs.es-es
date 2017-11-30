---
title: Operadores bit a bit (F#)
description: "Obtenga información acerca de los operadores bit a bit que están disponibles en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8a2c87f5-b4c7-47fe-8580-82c956f605e5
ms.openlocfilehash: 61a8e6bafe97a229480c967a4afb5d2a256474c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="bitwise-operators"></a><span data-ttu-id="81c7f-104">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="81c7f-104">Bitwise Operators</span></span>

<span data-ttu-id="81c7f-105">En este tema se describe los operadores bit a bit que están disponibles en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="81c7f-105">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="81c7f-106">Resumen de operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="81c7f-106">Summary of Bitwise Operators</span></span>
<span data-ttu-id="81c7f-107">En la tabla siguiente describe los operadores bit a bit que se admiten para los tipos enteros con conversión unboxing en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="81c7f-107">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="81c7f-108">Operador</span><span class="sxs-lookup"><span data-stu-id="81c7f-108">Operator</span></span>|<span data-ttu-id="81c7f-109">Notas</span><span class="sxs-lookup"><span data-stu-id="81c7f-109">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="81c7f-110">Operador AND bit a bit.</span><span class="sxs-lookup"><span data-stu-id="81c7f-110">Bitwise AND operator.</span></span> <span data-ttu-id="81c7f-111">Bits del resultado tienen el valor 1 si y solo si los bits correspondientes en ambos operandos de origen son 1.</span><span class="sxs-lookup"><span data-stu-id="81c7f-111">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="81c7f-112">Operador OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="81c7f-112">Bitwise OR operator.</span></span> <span data-ttu-id="81c7f-113">Bits del resultado tienen el valor 1 si el valor de los bits correspondientes en el origen de los operandos son 1.</span><span class="sxs-lookup"><span data-stu-id="81c7f-113">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="81c7f-114">Bit a bit operador OR exclusivo.</span><span class="sxs-lookup"><span data-stu-id="81c7f-114">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="81c7f-115">Bits del resultado tienen el valor 1 si y solo si los bits en los operandos de origen tienen valores distintos.</span><span class="sxs-lookup"><span data-stu-id="81c7f-115">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="81c7f-116">Operador de negación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="81c7f-116">Bitwise negation operator.</span></span> <span data-ttu-id="81c7f-117">Esto es un operador unario y genera un resultado en el que todos los bits 0 del operando de origen se convierten en bits 1 y todos los bits 1 se convierten en bits 0.</span><span class="sxs-lookup"><span data-stu-id="81c7f-117">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="81c7f-118">Bit a bit el operador de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="81c7f-118">Bitwise left-shift operator.</span></span> <span data-ttu-id="81c7f-119">El resultado es que el primer operando con bits desplazado a la izquierda el número de bits del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="81c7f-119">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="81c7f-120">Bits desplazados fuera de la posición más importante no se pasan a la posición menos significativa.</span><span class="sxs-lookup"><span data-stu-id="81c7f-120">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="81c7f-121">Los bits menos significativos se rellenan con ceros.</span><span class="sxs-lookup"><span data-stu-id="81c7f-121">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="81c7f-122">El tipo del segundo argumento es `int32`.</span><span class="sxs-lookup"><span data-stu-id="81c7f-122">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="81c7f-123">Bit a bit el operador de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="81c7f-123">Bitwise right-shift operator.</span></span> <span data-ttu-id="81c7f-124">El resultado es el primer operando con los bits que se desplazan a la derecha el número de bits del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="81c7f-124">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="81c7f-125">Los bits desplazados fuera de la posición menos significativa no se pasan en la posición más significativa.</span><span class="sxs-lookup"><span data-stu-id="81c7f-125">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="81c7f-126">Para los tipos sin signo, los bits más significativos se rellenan con ceros.</span><span class="sxs-lookup"><span data-stu-id="81c7f-126">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="81c7f-127">Para los tipos con signo, los bits más significativos se rellenan con los.</span><span class="sxs-lookup"><span data-stu-id="81c7f-127">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="81c7f-128">El tipo del segundo argumento es `int32`.</span><span class="sxs-lookup"><span data-stu-id="81c7f-128">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="81c7f-129">Los tipos siguientes se pueden utilizar con operadores bit a bit: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, y `unativeint`.</span><span class="sxs-lookup"><span data-stu-id="81c7f-129">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="81c7f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="81c7f-130">See Also</span></span>
[<span data-ttu-id="81c7f-131">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="81c7f-131">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="81c7f-132">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="81c7f-132">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="81c7f-133">Operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="81c7f-133">Boolean Operators</span></span>](boolean-operators.md)

