---
title: Single (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c91dbdf73ed1e26393518001ec8651557e5b780f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="single-data-type-visual-basic"></a>Single (Tipo de datos, Visual Basic)
Contiene con signo números de punto flotante IEEE 32 bits (4 bytes) precisión sencilla que abarcan un valor de - 3, 4028235E + 38 a - 1, 401298E-45 para los valores negativos y entre 1, 401298E-45 a 3, 4028235E + 38 para valores positivos. Los números de precisión sencilla almacenan una aproximación de un número real.  
  
## <a name="remarks"></a>Comentarios  
 Use la `Single` tipo de datos para contener valores de punto flotante que no requieren el ancho completo de datos de `Double`. En algunos casos, common language runtime podrían llevar empaquetar su `Single` variables estrecha colaboración y ahorre consumo de memoria.  
  
 El valor predeterminado de `Single` es 0.  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Precisión.** Cuando trabaje con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en memoria. Esto podría provocar resultados inesperados en ciertas operaciones, como comparación de valores y la `Mod` operador. Para obtener más información, consulte [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **De ampliación.** El `Single` tipo de datos se amplía a `Double`. Esto significa que se puede convertir `Single` a `Double` sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
-   **Ceros finales.** Los tipos de datos de punto flotante no tiene una representación interna de caracteres 0 finales. Por ejemplo, no distinguen entre 4,2000 y 4,2. Por lo tanto, los caracteres 0 finales no aparecen al mostrar o imprimir valores de punto flotante.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `F` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Single`. Si se agrega el carácter de tipo identificador `!` a cualquier identificador, se convierte forzosamente al tipo `Single`.  
  
-   **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Single?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Single?displayProperty=nameWithType>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Decimal (tipo de datos)](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Double (tipos de datos)](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
