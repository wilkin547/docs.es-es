---
title: 'Cómo: Convertir cadenas hexadecimales en números (Visual Basic)'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: 65184bbb742ad549a8398d55dc7bdeed05a9d973
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50048559"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Cómo: Convertir cadenas hexadecimales en números (Visual Basic)
En este ejemplo convierte una cadena hexadecimal en un entero con el <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> método.  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Para convertir una cadena hexadecimal en un número  
  
-   Use el <xref:System.Convert.ToInt32(System.String,System.Int32)> método para convertir el número expresado en base 16 en un entero.  
  
     El primer argumento de la <xref:System.Convert.ToInt32(System.String,System.Int32)> método es la cadena para convertir. El segundo argumento describe la base en que el número se expresa en; hexadecimal es base 16.  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- Tenga en cuenta que la cadena hexadecimal tiene las siguientes restricciones:

   - No puede incluir el `&h` prefijo.
   - No puede incluir el `_` separador de dígitos.

   Si el prefijo o un separador de dígitos está presente, la llamada a la <xref:System.Convert.ToInt32(System.String,System.Int32)> método produce una <xref:System.FormatException>.

## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
