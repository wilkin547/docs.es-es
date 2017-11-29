---
title: "Tipos de datos numéricos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c185b7c04d589bfe74d1cca0c60df3e81ab80d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="numeric-data-types-visual-basic"></a>Tipos de datos numéricos (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]proporciona varios *tipos de datos numéricos* para controlar números en varias representaciones. *Entero* tipos representan sólo números enteros (positivos, negativos y cero), y *no integrales* tipos representan números con entero y fracción.  
  
 Para una tabla que muestra una comparación en paralelo de la [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] tipos de datos, consulte [tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="integral-numeric-types"></a>Tipos numéricos integrales  
 *Tipos de datos integrales* son aquellos que sólo representan números sin partes fraccionarias.  
  
 El *firmado* son tipos de datos integrales [tipo de datos SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 bits), [Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16 bits), [tipo de datos entero](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32 bits) y [ Tipo de datos Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64 bits). Si una variable almacena siempre enteros en lugar de números fraccionarios, declárela como uno de estos tipos.  
  
 El *sin signo* tipos enteros son [tipo de datos Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 bits), [tipo de datos UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16 bits), [tipo de datos UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 bits) y [ Tipo de datos ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64 bits). Si una variable contiene datos binarios o datos de naturaleza desconocida, declárela como uno de estos tipos.  
  
### <a name="performance"></a>Rendimiento  
 Operaciones aritméticas son más rápidas con tipos integrales que con otros tipos de datos. Son más rápidos con los `Integer` y `UInteger` tipos de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
### <a name="large-integers"></a>Números enteros grandes  
 Si necesita contener un número entero mayor que el `Integer` puede contener el tipo de datos, puede usar el `Long` en su lugar, el tipo de datos. `Long`las variables pueden contener números de -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807. Operaciones con `Long` son ligeramente más lentas que con `Integer`.  
  
 Si necesita valores aun más grandes, puede usar el [tipo de datos Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). Puede contener números de -79.228.162.514.264.337.593.543.950,335 a 79,228,162,514,264,337,593,543,950,335 en un `Decimal` variable si no utiliza las posiciones decimales. Sin embargo, las operaciones con `Decimal` números son considerablemente más lentos que con cualquier otro tipo de datos numéricos.  
  
### <a name="small-integers"></a>Pequeños enteros  
 Si no necesita el intervalo completo de la `Integer` tipo de datos, puede usar el `Short` tipo de datos, que puede contener números enteros comprendidos entre -32.768 y 32.767. Para el intervalo entero más pequeño, el `SByte` tipo de datos contiene números enteros de -128 a 127. Si tiene un gran número de variables que contienen pequeños enteros, common language runtime puede almacenar a veces la `Short` y `SByte` variables de forma más eficaz y ahorre consumo de memoria. Sin embargo, las operaciones con `Short` y `SByte` son un poco más lento que con `Integer`.  
  
### <a name="unsigned-integers"></a>Enteros sin signo  
 Si sabe que la variable nunca debe contener un número negativo, puede usar el *tipos sin signo*`Byte`, `UShort`, `UInteger`, y `ULong`. Cada uno de estos tipos de datos puede contener un número entero positivo dos veces tan grande como un tipo con signo correspondiente (`SByte`, `Short`, `Integer`, y `Long`). En términos de rendimiento, cada tipo sin signo es exactamente tan eficaz como su tipo con signo correspondiente. En concreto, `UInteger` comparte con `Integer` la distinción de ser más eficaz de todos los tipos de datos numéricos básicos.  
  
## <a name="nonintegral-numeric-types"></a>Tipos numéricos enteros  
 *Tipos de datos enteros* son aquellos que representan números con entero y fracción.  
  
 Los tipos de datos numéricos no integrales son `Decimal` (punto fijo de 128 bits), [único tipo de datos](../../../../visual-basic/language-reference/data-types/single-data-type.md) (punto flotante de 32 bits), y [tipo de datos Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (punto flotante de 64 bits). Son tipos todos firmados. Si una variable puede contener una fracción, declárela como uno de estos tipos.  
  
 `Decimal`no es un tipo de datos de punto flotante. `Decimal`los números tienen un valor entero binario y un factor de escala de entero que especifica qué parte del valor es una fracción decimal.  
  
 Puede usar `Decimal` variables para valores de moneda. La ventaja es la precisión de los valores. El `Double` tipo de datos es más rápido y requiere menos memoria, pero está sujeto a errores de redondeo. El `Decimal` tipo de datos proporciona una exactitud total en 28 posiciones decimales.  
  
 Punto flotante (`Single` y `Double`) números tienen intervalos mayores que `Decimal` números, pero puede estar sujeto a errores de redondeo. Tipos de punto flotante admiten menos dígitos significativos que `Decimal` pero pueden representar valores de mayor magnitud.  
  
 Valores numéricos se pueden expresar como mmmEeee, en que mmm es la *mantisa* (los dígitos significativos) y eee es el *exponente* (una potencia de 10). Los valores positivos superiores de los tipos enteros son 7.9228162514264337593543950335E + 28 para `Decimal`, 3, 4028235E + 38 para `Single`y 1, 79769313486231570E + 308 para `Double`.  
  
### <a name="performance"></a>Rendimiento  
 `Double`es el más eficaz de los tipos de datos fraccionarios, porque los procesadores en las plataformas actuales realizan operaciones de punto flotante de precisión doble. Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.  
  
### <a name="small-magnitudes"></a>Magnitudes pequeñas  
 Para los números con la magnitud más pequeña posible (cercana a 0), `Double` las variables pueden contener números tan pequeños como - 4, 94065645841246544E-324 para valores negativos y 4, 94065645841246544E-324 para valores positivos.  
  
### <a name="small-fractional-numbers"></a>Números fraccionarios pequeños  
 Si no necesita el intervalo completo de la `Double` tipo de datos, puede usar el `Single` tipo de datos, que puede contener números de punto flotante de - 3, 4028235E + 38 a 3, 4028235E + 38. Las magnitudes más pequeñas para `Single` las variables son - 1, 401298E-45 para valores negativos y 1, 401298E-45 para valores positivos. Si tiene un gran número de variables que contienen números de punto flotante pequeños, common language runtime puede almacenar a veces su `Single` variables de forma más eficaz y ahorre consumo de memoria.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipos de datos de caracteres](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Tipos de datos varios](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Llamar a una función de Windows que adopta tipos sin signo](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
