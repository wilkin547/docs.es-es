---
title: Decimal (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55a9293fa680a7a04cff4099654d4d66790e8d3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="decimal-data-type-visual-basic"></a>Decimal (Tipo de datos, Visual Basic)
Contiene con signo valores de 128 bits (16 bytes) que representan números enteros de 96 bits (12 bytes) escalados por una potencia variable de 10. El factor de escala especifica el número de dígitos a la derecha del separador decimal; lo comprendido entre 0 y 28. Con una escala de 0 (sin decimales), el mayor valor posible es +/-79,228,162,514,264,337,593,543,950,335 (+/-7. 9228162514264337593543950335E + 28). Con 28 decimales, el mayor valor posible es +/-7,9228162514264337593543950335 y el valor más pequeño distinto de cero es +/-0.0000000000000000000000000001 (+/-1E-28).  
  
## <a name="remarks"></a>Comentarios  
 El `Decimal` tipo de datos proporciona el mayor número de dígitos significativos para un número. Admite hasta 29 dígitos significativos y puede representar valores que superan 7,9228 x 10 ^ 28. Es especialmente adecuado para los cálculos, como financieros, que requieren un gran número de dígitos pero no puede tolerar errores de redondeo.  
  
 El valor predeterminado de `Decimal` es 0.  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Precisión.** `Decimal`no es un tipo de datos de punto flotante. El `Decimal` estructura contiene un valor entero binario, junto con un bit de signo y un entero factor de escala que especifica qué parte del valor es una fracción decimal. Por este motivo, `Decimal` números tienen una representación más precisa en la memoria que los tipos de punto flotante (`Single` y `Double`).  
  
-   **Rendimiento.** El `Decimal` tipo de datos es el más lento de todos los tipos numéricos. Debería sopesar la importancia de la precisión con respecto al rendimiento antes de elegir un tipo de datos.  
  
-   **De ampliación.** El `Decimal` tipo de datos se amplía a `Single` o `Double`. Esto significa que se puede convertir `Decimal` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
-   **Ceros finales.** Visual Basic no almacena los ceros finales en un `Decimal` literal. Sin embargo, un `Decimal` variable conserva todos los ceros finales adquiridos mediante cálculos. Esto se ilustra en el siguiente ejemplo:  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     La salida de `MsgBox` en el ejemplo anterior es la siguiente:  
  
     D1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `D` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Decimal`. Si se agrega el carácter de tipo identificador `@` a cualquier identificador, se convierte forzosamente al tipo `Decimal`.  
  
-   **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Decimal?displayProperty=nameWithType>.  
  
## <a name="range"></a>Intervalo  
 Quizás necesite utilizar el `D` escriba el carácter que se va a asignar un valor grande para un `Decimal` variable o constante. Este requisito es porque el compilador interpreta un literal como `Long` a menos que un carácter de tipo literal sigue el literal, como se muestra en el ejemplo siguiente.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 La declaración de `bigDec1` no genera un desbordamiento porque el valor que se asigna a la se encuentra dentro del intervalo de `Long`. El `Long` valor puede asignarse a la `Decimal` variable.  
  
 La declaración de `bigDec2` genera un error de desbordamiento porque es demasiado grande para el valor que se asigna a ella `Long`. Dado que el literal numérico en primer lugar no se puede interpretar como un `Long`, no se puede asignar a la `Decimal` variable.  
  
 Para `bigDec3`, el carácter de tipo literal `D` se resuelve el problema, forzar al compilador que interprete el literal como una `Decimal` en lugar de como un `Long`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Single (tipo de datos)](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Double (tipos de datos)](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
