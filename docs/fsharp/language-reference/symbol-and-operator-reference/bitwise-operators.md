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
# <a name="bitwise-operators"></a>Operadores bit a bit

En este tema se describe los operadores bit a bit que están disponibles en el lenguaje F #.

## <a name="summary-of-bitwise-operators"></a>Resumen de operadores bit a bit
En la tabla siguiente describe los operadores bit a bit que se admiten para los tipos enteros con conversión unboxing en el lenguaje F #.

|Operador|Notas|
|--------|-----|
|`&&&`|Operador AND bit a bit. Bits del resultado tienen el valor 1 si y solo si los bits correspondientes en ambos operandos de origen son 1.|
|<code>&#124;&#124;&#124;</code>|Operador OR bit a bit. Bits del resultado tienen el valor 1 si el valor de los bits correspondientes en el origen de los operandos son 1.|
|`^^^`|Bit a bit operador OR exclusivo. Bits del resultado tienen el valor 1 si y solo si los bits en los operandos de origen tienen valores distintos.|
|`~~~`|Operador de negación bit a bit. Esto es un operador unario y genera un resultado en el que todos los bits 0 del operando de origen se convierten en bits 1 y todos los bits 1 se convierten en bits 0.|
|`<<<`|Bit a bit el operador de desplazamiento a la izquierda. El resultado es que el primer operando con bits desplazado a la izquierda el número de bits del segundo operando. Bits desplazados fuera de la posición más importante no se pasan a la posición menos significativa. Los bits menos significativos se rellenan con ceros. El tipo del segundo argumento es `int32`.|
|`>>>`|Bit a bit el operador de desplazamiento a la derecha. El resultado es el primer operando con los bits que se desplazan a la derecha el número de bits del segundo operando. Los bits desplazados fuera de la posición menos significativa no se pasan en la posición más significativa. Para los tipos sin signo, los bits más significativos se rellenan con ceros. Para los tipos con signo, los bits más significativos se rellenan con los. El tipo del segundo argumento es `int32`.|

Los tipos siguientes se pueden utilizar con operadores bit a bit: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, y `unativeint`.

## <a name="see-also"></a>Vea también
[Referencia de símbolos y operadores](index.md)

[Operadores aritméticos](arithmetic-operators.md)

[Operadores booleanos](boolean-operators.md)

