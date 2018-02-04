---
title: "Cómo: Convertir cadenas hexadecimales en números (Visual Basic)"
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: petrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: c35ac615e3f87710f934a1cf66e6546625298bd0
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Cómo: Convertir cadenas hexadecimales en números (Visual Basic)
Este ejemplo convierte una cadena hexadecimal en un entero con el <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> método.  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Para convertir una cadena hexadecimal en un número  
  
-   Use la <xref:System.Convert.ToInt32(System.String,System.Int32)> método para convertir el número expresado en base 16 a un entero.  
  
     El primer argumento de la <xref:System.Convert.ToInt32(System.String,System.Int32)> método es la cadena que se va a convertir. El segundo argumento describe la base en que el número se expresa en; hexadecimal es base 16.  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- Tenga en cuenta que la cadena hexadecimal tiene las siguientes restricciones:

   - No puede incluir el `&h` prefijo.
   - No puede incluir el `_` separador de dígitos.

   Si el prefijo o un separador de dígitos está presente, la llamada a la <xref:System.Convert.ToInt32(System.String,System.Int32)> método produce un <xref:System.FormatException>.

## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
