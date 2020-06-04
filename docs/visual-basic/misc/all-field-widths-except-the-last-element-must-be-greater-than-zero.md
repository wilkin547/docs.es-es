---
title: Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: 0e81652a0f9e97ce40851170ed050bd1f047ba5f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412941"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero.
Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero. Un ancho de campo menor o igual que cero en el último elemento indica que el último campo es de longitud variable.  
  
 Error en la operación porque un ancho de campo distinto del último elemento está establecido en cero o menos. Un ancho de campo menor o igual que cero se puede usar como último elemento para indicar que el último campo es de longitud variable, pero no se puede usar como cualquier otro elemento.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Establezca el ancho de campo en la longitud correcta.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [Procedimiento para leer archivos de texto de ancho fijo](../developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
