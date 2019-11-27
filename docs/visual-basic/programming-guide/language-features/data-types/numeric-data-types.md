---
title: Tipos de datos numéricos
ms.date: 07/20/2015
helpviewer_keywords:
- integral types [Visual Basic], Visual Basic
- Short data type [Visual Basic], numeric data types
- Double data type [Visual Basic], numeric data types
- Long data type [Visual Basic], Visual Basic numeric data types
- numbers [Visual Basic], whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers [Visual Basic], integer
- fractional data types [Visual Basic]
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type [Visual Basic], numeric data types
- exponent, of fractional numbers
- integers [Visual Basic]
- numeric data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], numeric types
- Decimal data type [Visual Basic], numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
ms.openlocfilehash: dc8b630eebc48e5733344a00664b453360769c0b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346307"
---
# <a name="numeric-data-types-visual-basic"></a>Tipos de datos numéricos (Visual Basic)
Visual Basic proporciona varios *tipos de datos numéricos* para administrar números en varias representaciones. Los tipos *enteros* representan solo números enteros (positivos, negativos y cero), y los tipos no *enteros* representan números con valores enteros y fraccionarios.  
  
 Para ver una tabla que muestra una comparación en paralelo de los tipos de datos Visual Basic, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Tipos numéricos enteros  
 Los *tipos de datos enteros* son aquellos que solo representan números sin partes fraccionarias.  
  
 Los tipos de datos enteros *con signo* son el [tipo de datos sbyte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 bits), el [tipo de datos Short](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16 bits), el [tipo de datos Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32 bits) y el [tipo de datos Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64 bits). Si una variable siempre almacena enteros en lugar de números fraccionarios, declárelo como uno de estos tipos.  
  
 Los tipos enteros *sin signo* son el [tipo de datos byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 bits), el [tipo de datos ushort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16 bits), el [tipo de datos UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 bits) y el [tipo de datos ulong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64 bits). Si una variable contiene datos binarios o datos de naturaleza desconocida, declárelo como uno de estos tipos.  
  
### <a name="performance"></a>Rendimiento  
 Las operaciones aritméticas son más rápidas con tipos enteros que con otros tipos de datos. Son más rápidos con los tipos `Integer` y `UInteger` de Visual Basic.  
  
### <a name="large-integers"></a>Enteros grandes  
 Si necesita contener un entero mayor que el `Integer` puede contener el tipo de datos, puede utilizar el tipo de datos `Long` en su lugar. `Long` variables pueden contener números comprendidos entre-9.223.372.036.854.775.808 y 9.223.372.036.854.775.807. Las operaciones con `Long` son ligeramente más lentas que con `Integer`.  
  
 Si necesita valores incluso mayores, puede usar el tipo de [datos decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Puede contener números entre-79.228.162.514.264.337.593.543.950.335 y 79.228.162.514.264.337.593.543.950.335 en una variable `Decimal` si no usa ninguna posición decimal. Sin embargo, las operaciones con números `Decimal` son considerablemente más lentas que con cualquier otro tipo de datos numéricos.  
  
### <a name="small-integers"></a>Enteros pequeños  
 Si no necesita el intervalo completo del tipo de datos `Integer`, puede usar el tipo de datos `Short`, que puede contener enteros de-32.768 a 32.767. En el intervalo de enteros más pequeño, el tipo de datos `SByte` contiene enteros de-128 a 127. Si tiene un número muy grande de variables que contienen pequeños enteros, en ocasiones, el Common Language Runtime puede almacenar las variables `Short` y `SByte` de manera más eficaz y ahorrar consumo de memoria. Sin embargo, las operaciones con `Short` y `SByte` son ligeramente más lentas que con `Integer`.  
  
### <a name="unsigned-integers"></a>Enteros sin signo  
 Si sabe que la variable nunca necesita contener un número negativo, puede usar los *tipos sin signo*`Byte`, `UShort`, `UInteger`y `ULong`. Cada uno de estos tipos de datos puede contener un entero positivo dos veces mayor que el tipo con signo correspondiente (`SByte`, `Short`, `Integer`y `Long`). En cuanto al rendimiento, cada tipo sin signo es exactamente tan eficaz como su tipo con signo correspondiente. En concreto, `UInteger` recursos compartidos con `Integer` la distinción de ser el más eficaz de todos los tipos de datos numéricos elementales.  
  
## <a name="nonintegral-numeric-types"></a>Tipos numéricos no enteros  
 Los *tipos de datos no integrales* son aquellos que representan números con enteros y partes fraccionarias.  
  
 Los tipos de datos numéricos no integrales son `Decimal` (punto fijo de 128 bits), [tipo de datos único](../../../../visual-basic/language-reference/data-types/single-data-type.md) (punto flotante de 32 bits) y [tipo de datos Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (punto flotante de 64 bits). Todos ellos son tipos firmados. Si una variable puede contener una fracción, declárela como uno de estos tipos.  
  
 `Decimal` no es un tipo de datos de punto flotante. los números `Decimal` tienen un valor entero binario y un factor de escala entero que especifica qué parte del valor es una fracción decimal.  
  
 Puede usar variables de `Decimal` para valores de moneda. La ventaja es la precisión de los valores. El tipo de datos `Double` es más rápido y requiere menos memoria, pero está sujeto a errores de redondeo. El tipo de datos `Decimal` conserva una precisión completa de 28 posiciones decimales.  
  
 Los números de punto flotante (`Single` y `Double`) tienen intervalos mayores que `Decimal` números, pero pueden estar sujetos a errores de redondeo. Los tipos de punto flotante admiten menos dígitos significativos que `Decimal` pero pueden representar valores de mayor magnitud.  
  
 Los valores de número no integral se pueden expresar como mmmEeee, en los que MMM es la *mantisa* (los dígitos significativos) y EEE es el *exponente* (una potencia de 10). Los valores positivos más altos de los tipos no integrales son 7,9228162514264337593543950335 E + 28 para `Decimal`, 3.4028235 E + 38 para `Single`y 1.79769313486231570 E + 308 para `Double`.  
  
### <a name="performance"></a>Rendimiento  
 `Double` es el más eficaz de los tipos de datos fraccionarios, ya que los procesadores de las plataformas actuales realizan operaciones de punto flotante de doble precisión. Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.  
  
### <a name="small-magnitudes"></a>Pequeñas magnitudes  
 En el caso de los números con la menor magnitud posible (más cercana a 0), `Double` variables pueden contener números tan pequeños como-4.94065645841246544 E-324 para los valores negativos y 4.94065645841246544 E-324 para los valores positivos.  
  
### <a name="small-fractional-numbers"></a>Números fraccionarios pequeños  
 Si no necesita el intervalo completo del tipo de datos `Double`, puede usar el tipo de datos `Single`, que puede contener números de punto flotante de-3.4028235 E + 38 a 3.4028235 E + 38. Las magnitudes más pequeñas de las variables de `Single` son-401298e E-45 para los valores negativos y 401298e E-45 para los valores positivos. Si tiene un número muy grande de variables que contienen números de punto flotante pequeños, a veces el Common Language Runtime puede almacenar las variables `Single` de forma más eficaz y ahorrar consumo de memoria.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de datos de caracteres](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Tipos de datos varios](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Llamar a una función de Windows que adopta tipos sin signo](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
