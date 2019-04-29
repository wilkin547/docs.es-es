---
title: Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: 806dcef7b7a29afa8804a581659023c817662434
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940665"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero.
Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero. Un ancho de campo menor o igual que cero en el último elemento indica que el último campo es de longitud variable.  
  
 Error en la operación porque un ancho de campo distinto del último elemento está establecido en cero o menos. Un ancho de campo menor o igual que cero se puede usar como último elemento para indicar que el último campo es de longitud variable, pero no se puede usar como cualquier otro elemento.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Establezca el ancho de campo en la longitud correcta.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [Cómo: Leer archivos de texto de ancho fijo](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [TextFieldParser (objeto)](../../visual-basic/language-reference/objects/textfieldparser-object.md)
