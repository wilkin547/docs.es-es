---
title: Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: c1537133300ac4de33d0d7ebc3ea0ad6768e8ec9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609145"
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
