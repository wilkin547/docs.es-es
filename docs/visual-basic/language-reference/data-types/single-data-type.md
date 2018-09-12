---
title: Single (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 98433c0f1d1008664bb994f3b43fe48a753a432c
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44511648"
---
# <a name="single-data-type-visual-basic"></a>Single (Tipo de datos, Visual Basic)
Contiene con signo de números de punto flotante IEEE 32 bits (4 bytes) precisión sencilla que van de - 3, 4028235E + 38 a - 1, 401298E-45 para los valores negativos y de 1, 401298E-45 a 3, 4028235E + 38 para los valores positivos. Números de precisión sencilla almacenan una aproximación de un número real.  
  
## <a name="remarks"></a>Comentarios  
 Use la `Single` tipo de datos para contener valores de punto flotante que no requieren el ancho completo de datos de `Double`. En algunos casos, common language runtime podría ser capaz de empaquetar su `Single` variables juntas y ahorrar consumo de memoria.  
  
 El valor predeterminado de `Single` es 0.  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Precisión.** Cuando se trabaja con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en memoria. Esto podría provocar resultados inesperados en ciertas operaciones, como la comparación de valor y el `Mod` operador. Para obtener más información, consulte [solución de problemas de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Ampliación.** El `Single` tipo de datos se amplía a `Double`. Esto significa que se puede convertir `Single` a `Double` sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
-   **Ceros finales.** Los tipos de datos de punto flotante no tienen una representación interna de los caracteres 0 finales. Por ejemplo, no distinguen entre 4,2000 y 4,2. Por lo tanto, los caracteres 0 finales no aparecen al mostrar o imprimir valores de punto flotante.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `F` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Single`. Si se agrega el carácter de tipo identificador `!` a cualquier identificador, se convierte forzosamente al tipo `Single`.  
  
-   **Tipo de marco de trabajo.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Single?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Single?displayProperty=nameWithType>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)  
 [Decimal (tipo de datos)](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Double (tipos de datos)](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
