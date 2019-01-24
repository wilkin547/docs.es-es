---
title: Double (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 456383dd2f38e96a8ff18472ff44c65ba7b4a341
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626490"
---
# <a name="double-data-type-visual-basic"></a>Double (Tipo de datos, Visual Basic)
Contiene números con signo IEEE de 64 bits (8 bytes) precisión doble punto flotante que intervalo entre - 1, 79769313486231570E + 308 a - 4, 94065645841246544E-324 para los valores negativos y de 4, 94065645841246544E-324 a 1, 79769313486231570E + 308 para valores positivos. Números de precisión doble almacenan una aproximación de un número real.  
  
## <a name="remarks"></a>Comentarios  
 El `Double` tipo de datos proporciona las magnitudes más grandes y más pequeño posibles para un número.  
  
 El valor predeterminado de `Double` es 0.  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Precisión.** Cuando se trabaja con números de punto flotante, recuerde que no siempre tienen una representación precisa en memoria. Esto podría provocar resultados inesperados en ciertas operaciones, como la comparación de valor y el `Mod` operador. Para obtener más información, consulte [solución de problemas de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Ceros finales.** Los tipos de datos de punto flotante no tienen una representación interna de cero caracteres finales. Por ejemplo, no distinguen entre 4,2000 y 4,2. Por lo tanto, cero caracteres finales no aparecen cuando se muestren o valores de punto flotante de impresión.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `R` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Double`. Por ejemplo, si un valor entero seguido `R`, el valor se cambia a un `Double`.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     Si se agrega el carácter de tipo identificador `#` a cualquier identificador, se convierte forzosamente al tipo `Double`. En el ejemplo siguiente, la variable `num` se escribe como un `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Tipo de marco de trabajo.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Double?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Double?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Decimal (tipo de datos)](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Single (tipo de datos)](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
