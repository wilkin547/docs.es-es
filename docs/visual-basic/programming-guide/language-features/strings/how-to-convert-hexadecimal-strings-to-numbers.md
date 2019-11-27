---
title: 'Cómo: Convertir cadenas hexadecimales en números'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347170"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Cómo: Convertir cadenas hexadecimales en números (Visual Basic)

En este ejemplo se convierte una cadena hexadecimal en un entero mediante el método <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>.

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Para convertir una cadena hexadecimal en un número

- Use el método <xref:System.Convert.ToInt32(System.String,System.Int32)> para convertir el número expresado en base-16 en un entero.

  El primer argumento del método <xref:System.Convert.ToInt32(System.String,System.Int32)> es la cadena que se va a convertir. El segundo argumento describe en qué base se expresa el número; hexadecimal es base 16.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- Tenga en cuenta que la cadena hexadecimal tiene las restricciones siguientes:

  - No puede incluir el prefijo `&h`.
  - No puede incluir el separador de dígitos `_`.

  Si el prefijo o el separador de dígitos están presentes, la llamada al método <xref:System.Convert.ToInt32(System.String,System.Int32)> produce una <xref:System.FormatException>.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
