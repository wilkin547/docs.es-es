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
ms.openlocfilehash: 72cdca295e209935687f67ad290e816775d9fe13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393681"
---
# <a name="numeric-data-types-visual-basic"></a>Tipos de datos numéricos (Visual Basic)
Visual Basic proporciona varios *tipos de datos numéricos* para administrar números en varias representaciones. Los tipos *enteros* representan solo números enteros (positivos, negativos y cero), y los tipos no *enteros* representan números con valores enteros y fraccionarios.  
  
 Para ver una tabla que muestra una comparación en paralelo de los tipos de datos Visual Basic, vea [tipos de datos](../../../language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Tipos numéricos enteros  
 Los *tipos de datos enteros* son aquellos que solo representan números sin partes fraccionarias.  
  
 Los tipos de datos enteros *con signo* son el [tipo de datos sbyte](../../../language-reference/data-types/sbyte-data-type.md) (8 bits), el [tipo de datos Short](../../../language-reference/data-types/short-data-type.md) (16 bits), el [tipo de datos Integer](../../../language-reference/data-types/integer-data-type.md) (32 bits) y el [tipo de datos Long](../../../language-reference/data-types/long-data-type.md) (64 bits). Si una variable siempre almacena enteros en lugar de números fraccionarios, declárelo como uno de estos tipos.  
  
 Los tipos enteros *sin signo* son el [tipo de datos byte](../../../language-reference/data-types/byte-data-type.md) (8 bits), el [tipo de datos ushort](../../../language-reference/data-types/ushort-data-type.md) (16 bits), el [tipo de datos UInteger](../../../language-reference/data-types/uinteger-data-type.md) (32 bits) y el [tipo de datos ulong](../../../language-reference/data-types/ulong-data-type.md) (64 bits). Si una variable contiene datos binarios o datos de naturaleza desconocida, declárelo como uno de estos tipos.  
  
### <a name="performance"></a>Rendimiento  
 Las operaciones aritméticas son más rápidas con tipos enteros que con otros tipos de datos. Son más rápidos con los `Integer` tipos y `UInteger` en Visual Basic.  
  
### <a name="large-integers"></a>Enteros grandes  
 Si necesita contener un entero mayor que el `Integer` tipo de datos que puede contener, puede usar el tipo de `Long` datos en su lugar. `Long`las variables pueden contener números comprendidos entre-9.223.372.036.854.775.808 y 9.223.372.036.854.775.807. Las operaciones con `Long` son ligeramente más lentas que con `Integer` .  
  
 Si necesita valores incluso mayores, puede usar el tipo de [datos decimal](../../../language-reference/data-types/decimal-data-type.md). Puede contener números entre-79.228.162.514.264.337.593.543.950.335 y 79.228.162.514.264.337.593.543.950.335 en una `Decimal` variable si no usa ninguna posición decimal. Sin embargo, las operaciones con `Decimal` números son considerablemente más lentas que con cualquier otro tipo de datos numérico.  
  
### <a name="small-integers"></a>Enteros pequeños  
 Si no necesita el intervalo completo del `Integer` tipo de datos, puede usar el `Short` tipo de datos, que puede contener enteros de-32.768 a 32.767. En el intervalo de enteros más pequeño, el `SByte` tipo de datos contiene enteros de-128 a 127. Si tiene un número muy grande de variables que contienen pequeños enteros, en ocasiones, el Common Language Runtime puede almacenar las `Short` variables y de `SByte` forma más eficaz y ahorrar consumo de memoria. Sin embargo, las operaciones con `Short` y `SByte` son ligeramente más lentas que con `Integer` .  
  
### <a name="unsigned-integers"></a>Enteros sin signo  
 Si sabe que la variable nunca necesita contener un número negativo, puede usar los *tipos sin signo* `Byte` ,, `UShort` `UInteger` y `ULong` . Cada uno de estos tipos de datos puede contener un entero positivo dos veces mayor que el tipo con signo correspondiente ( `SByte` , `Short` , `Integer` y `Long` ). En cuanto al rendimiento, cada tipo sin signo es exactamente tan eficaz como su tipo con signo correspondiente. En concreto, los `UInteger` recursos compartidos con `Integer` la diferencia de ser el más eficaz de todos los tipos de datos numéricos básicos.  
  
## <a name="nonintegral-numeric-types"></a>Tipos numéricos no enteros  
 Los *tipos de datos no integrales* son aquellos que representan números con enteros y partes fraccionarias.  
  
 Los tipos de datos numéricos no enteros son `Decimal` (punto fijo de 128 bits), [un tipo de datos único](../../../language-reference/data-types/single-data-type.md) (punto flotante de 32 bits) y un [tipo de datos Double](../../../language-reference/data-types/double-data-type.md) (punto flotante de 64 bits). Todos ellos son tipos firmados. Si una variable puede contener una fracción, declárela como uno de estos tipos.  
  
 `Decimal`no es un tipo de datos de punto flotante. `Decimal`los números tienen un valor entero binario y un factor de escala entero que especifica qué parte del valor es una fracción decimal.  
  
 Puede usar `Decimal` variables para valores de moneda. La ventaja es la precisión de los valores. El `Double` tipo de datos es más rápido y requiere menos memoria, pero está sujeto a errores de redondeo. El `Decimal` tipo de datos conserva una precisión completa de 28 posiciones decimales.  
  
 Los números de punto flotante ( `Single` y `Double` ) tienen intervalos más grandes que `Decimal` números, pero pueden estar sujetos a errores de redondeo. Los tipos de punto flotante admiten menos dígitos significativos que `Decimal` pero pueden representar valores de mayor magnitud.  
  
 Los valores de número no integral se pueden expresar como mmmEeee, en los que MMM es la *mantisa* (los dígitos significativos) y EEE es el *exponente* (una potencia de 10). Los valores positivos más altos de los tipos no integrales son 7,9228162514264337593543950335 E + 28 para `Decimal` , 3.4028235 e + 38 para y `Single` 1.79769313486231570 e + 308 para `Double` .  
  
### <a name="performance"></a>Rendimiento  
 `Double`es el más eficaz de los tipos de datos fraccionarios, ya que los procesadores de las plataformas actuales realizan operaciones de punto flotante de doble precisión. Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer` .  
  
### <a name="small-magnitudes"></a>Pequeñas magnitudes  
 En el caso de los números con la menor magnitud posible (más cercana a 0), `Double` las variables pueden contener números tan pequeños como-4.94065645841246544 e-324 para los valores negativos y 4.94065645841246544 e-324 para los valores positivos.  
  
### <a name="small-fractional-numbers"></a>Números fraccionarios pequeños  
 Si no necesita el intervalo completo del `Double` tipo de datos, puede usar el `Single` tipo de datos, que puede contener números de punto flotante de-3.4028235 e + 38 a 3.4028235 e + 38. Las magnitudes más pequeñas de `Single` las variables son-401298E e-45 para los valores negativos y 401298E e-45 para los valores positivos. Si tiene un número muy grande de variables que contienen números de punto flotante pequeños, a veces el Common Language Runtime puede almacenar las `Single` variables de forma más eficaz y ahorrar consumo de memoria.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos básicos](elementary-data-types.md)
- [Tipos de datos de caracteres](character-data-types.md)
- [Tipos de datos varios](miscellaneous-data-types.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Procedimiento Llamada una función de Windows que adopta tipos sin signo](../../com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
