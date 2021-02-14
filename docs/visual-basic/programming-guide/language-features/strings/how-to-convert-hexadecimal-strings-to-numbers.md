---
description: 'Más información acerca de cómo: convertir cadenas hexadecimales en números (Visual Basic)'
title: Procedimiento para convertir cadenas hexadecimales en números
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: cf1648b5f85f189f203f56cf569041e4f2db5ac3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425548"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Cómo: Convertir cadenas hexadecimales en números (Visual Basic)

En este ejemplo se convierte una cadena hexadecimal en un entero mediante el <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> método.

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Para convertir una cadena hexadecimal en un número

- Use el <xref:System.Convert.ToInt32(System.String,System.Int32)> método para convertir el número expresado en base-16 en un entero.

  El primer argumento del <xref:System.Convert.ToInt32(System.String,System.Int32)> método es la cadena que se va a convertir. El segundo argumento describe en qué base se expresa el número; hexadecimal es base 16.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- Tenga en cuenta que la cadena hexadecimal tiene las restricciones siguientes:

  - No puede incluir el `&h` prefijo.
  - No puede incluir el `_` separador de dígitos.

  Si el prefijo o el separador de dígitos están presentes, la llamada al <xref:System.Convert.ToInt32(System.String,System.Int32)> método produce una excepción <xref:System.FormatException> .

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
