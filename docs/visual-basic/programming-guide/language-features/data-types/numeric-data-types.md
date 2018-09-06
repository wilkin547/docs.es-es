---
title: Tipos de datos numéricos (Visual Basic)
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
ms.openlocfilehash: 6578a410e389a313b0bad70f043691240e288887
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865763"
---
# <a name="numeric-data-types-visual-basic"></a>Tipos de datos numéricos (Visual Basic)
Visual Basic proporciona varios *tipos de datos numéricos* para controlar números en representaciones. *Entero* tipos representan sólo números enteros (positivos, negativos y cero), y *no integrales* tipos representan números con partes fraccionarias y enteras.  
  
 Para una tabla que muestra una comparación en paralelo de los tipos de datos de Visual Basic, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Tipos numéricos integrales  
 *Tipos de datos enteros* son aquellos que representan sólo números sin partes fraccionarias.  
  
 El *firmado* son tipos de datos enteros [tipo de datos SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 bits), [Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16 bits), [tipo de datos entero](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32 bits) y [ Tipo de datos Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64 bits). Si una variable siempre almacena números enteros en lugar de números fraccionarios, declárelo como uno de estos tipos.  
  
 El *sin signo* tipos enteros son [tipo de datos Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 bits), [tipo de datos UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16 bits), [tipo de datos UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 bits) y [ Tipo de datos ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64 bits). Si una variable contiene datos binarios o datos de naturaleza desconocida, declárelo como uno de estos tipos.  
  
### <a name="performance"></a>Rendimiento  
 Operaciones aritméticas son más rápidas con tipos integrales que con otros tipos de datos. Son más rápidos con la `Integer` y `UInteger` tipos en Visual Basic.  
  
### <a name="large-integers"></a>Enteros grandes  
 Si tiene que contener un número entero mayor que el `Integer` puede contener el tipo de datos, puede usar el `Long` del tipo de datos en su lugar. `Long` las variables pueden contener números comprendidos entre -9.223.372.036.854.775.808 y 9.223.372.036.854.775.807. Operaciones con `Long` son un poco más lento que con `Integer`.  
  
 Si necesita valores incluso mayores, puede usar el [tipo de datos Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Puede contener números de -79.228.162.514.264.337.593.543.950,335 a 79,228,162,514,264,337,593,543,950,335 en un `Decimal` variable si no utiliza las posiciones decimales. Sin embargo, las operaciones con `Decimal` números son considerablemente más lentos que con cualquier otro tipo de datos numéricos.  
  
### <a name="small-integers"></a>Pequeños enteros  
 Si no necesita la gama completa de la `Integer` tipo de datos, puede usar el `Short` tipo de datos que puede contener números enteros comprendidos entre -32.768 y 32.767. Para el intervalo entero más pequeño, el `SByte` tipo de datos contiene enteros entre -128 y 127. Si tiene un gran número de variables que contienen pequeños enteros, common language runtime puede almacenar a veces su `Short` y `SByte` variables de manera más eficaz y ahorrar consumo de memoria. Sin embargo, las operaciones con `Short` y `SByte` son un poco más lento que con `Integer`.  
  
### <a name="unsigned-integers"></a>Enteros sin signo  
 Si sabe que nunca la variable debe contener un número negativo, se puede usar el *tipos sin signo*`Byte`, `UShort`, `UInteger`, y `ULong`. Cada uno de estos tipos de datos puede contener un número entero positivo dos veces tan grandes como un tipo con signo correspondiente (`SByte`, `Short`, `Integer`, y `Long`). En términos de rendimiento, cada tipo sin signo es exactamente tan eficaz como su tipo con signo correspondiente. En concreto, `UInteger` comparte con `Integer` la distinción de ser más eficaz de todos los tipos de datos numéricos básicos.  
  
## <a name="nonintegral-numeric-types"></a>Tipos numéricos no integrales  
 *Tipos de datos no entero* son aquellos que representan números con partes fraccionarias y enteras.  
  
 Los tipos de datos numéricos no integrales son `Decimal` (punto fijo de 128 bits), [único tipo de datos](../../../../visual-basic/language-reference/data-types/single-data-type.md) (punto flotante de 32 bits), y [tipo de datos Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (punto flotante de 64 bits). Son tipos todos firmados. Si una variable puede contener una fracción, declárelo como uno de estos tipos.  
  
 `Decimal` no es un tipo de datos de punto flotante. `Decimal` los números tienen un valor entero binario y un factor de escala de entero que especifica qué parte del valor es una fracción decimal.  
  
 Puede usar `Decimal` variables para los valores de moneda. La ventaja es la precisión de los valores. El `Double` tipo de datos es más rápido y requiere menos memoria, pero está sujeto a errores de redondeo. El `Decimal` tipo de datos conserva la precisión completa con 28 posiciones decimales.  
  
 Punto flotante (`Single` y `Double`) números tienen intervalos mayores que `Decimal` números pero pueden estar sujetas a errores de redondeo. Tipos de punto flotante admiten menos dígitos significativos que `Decimal` pero pueden representar valores de magnitud mayor.  
  
 Los valores de números se pueden expresar como mmmEeee, en que mmm es la *mantisa* (los dígitos significativos) y eee es el *exponente* (una potencia de 10). Los valores positivos superiores de los tipos no integrales son 7.9228162514264337593543950335E + 28 para `Decimal`, 3, 4028235E + 38 para `Single`y 1, 79769313486231570E + 308 para `Double`.  
  
### <a name="performance"></a>Rendimiento  
 `Double` es el más eficaz de los tipos de datos fraccionarios, porque los procesadores en las plataformas actuales realizan operaciones de punto flotante de precisión doble. Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.  
  
### <a name="small-magnitudes"></a>Magnitudes pequeñas  
 Para números con la magnitud más pequeña posible (más cercano a 0), `Double` las variables pueden contener números tan pequeños como - 4, 94065645841246544E-324 para los valores negativos y 4, 94065645841246544E-324 para valores positivos.  
  
### <a name="small-fractional-numbers"></a>Números fraccionarios pequeños  
 Si no necesita la gama completa de la `Double` tipo de datos, puede usar el `Single` tipo de datos que puede contener números de punto flotante de - 3, 4028235E + 38 a 3, 4028235E + 38. Las magnitudes más pequeñas para `Single` las variables son - 1, 401298E-45 para los valores negativos y 1, 401298E-45 para los valores positivos. Si tiene un gran número de variables que contienen números de punto flotante pequeños, common language runtime puede almacenar a veces su `Single` variables de manera más eficaz y ahorrar consumo de memoria.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipos de datos de caracteres](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Tipos de datos varios](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Llamar a una función de Windows que adopta tipos sin signo](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
