---
title: Operadores bit a bit (F#)
description: 'Obtenga información sobre los operadores bit a bit que están disponibles en el lenguaje de programación F #.'
ms.date: 07/20/2018
ms.openlocfilehash: ed76fcf5f9c569a2f288cf260e99dc29fd65ef3b
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338059"
---
# <a name="bitwise-operators"></a>Operadores bit a bit

En este tema se describe los operadores bit a bit que están disponibles en el lenguaje F #.

## <a name="summary-of-bitwise-operators"></a>Resumen de los operadores bit a bit

En la tabla siguiente describe los operadores bit a bit que se admiten para los tipos enteros con conversión unboxing en el lenguaje F #.

|Operador|Notas|
|--------|-----|
|`&&&`|Operador AND bit a bit. Bits del resultado tienen el valor 1 si y solo si los bits correspondientes de ambos operandos de origen son 1.|
|<code>&#124;&#124;&#124;</code>|Operador OR bit a bit. Bits del resultado tienen el valor 1 si alguno de los bits correspondientes en el origen de los operandos son 1.|
|`^^^`|Bit a bit operador OR exclusivo. Bits del resultado tienen el valor 1 si y solo si los bits en los operandos de origen tienen valores distintos.|
|`~~~`|Operador de negación bit a bit. Esto es un operador unario y genera un resultado en el que todos los bits 0 en el operando de origen se convierten en bits 1 y todos los bits 1 se convierten en bits 0.|
|`<<<`|Bit a bit el operador de desplazamiento a la izquierda. El resultado es el primer operando con bits desplazado a la izquierda el número de bits en el segundo operando. No se giran bits desplazados fuera de la posición más significativa en el menos significativo. Los bits menos significativos se rellenan con ceros. El tipo del segundo argumento es `int32`.|
|`>>>`|Bit a bit el operador de desplazamiento a la derecha. El resultado es el primer operando con bits desplazado a la derecha el número de bits en el segundo operando. No se giran bits desplazados el menos significativo en la posición más significativa. Para los tipos sin signo, los bits más significativos se rellenan con ceros. Para los tipos con signo con valores negativos, los bits más significativos se rellenan con los. El tipo del segundo argumento es `int32`.|

Los tipos siguientes pueden utilizarse con operadores bit a bit: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, y `unativeint`.

## <a name="see-also"></a>Vea también

- [Referencia de símbolos y operadores](index.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Operadores booleanos](boolean-operators.md)
