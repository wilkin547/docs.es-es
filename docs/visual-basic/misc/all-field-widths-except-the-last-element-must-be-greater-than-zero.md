---
description: 'Más información sobre: todos los anchos de campo, excepto el último elemento, deben ser mayores que cero.'
title: Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: cf2edb21f017031c7dd333893d554353eceebe73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787388"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero.

Todos los anchos de campo, excepto el último elemento, deben ser mayores que cero. Un ancho de campo menor o igual que cero en el último elemento indica que el último campo es de longitud variable.  
  
 Error en la operación porque un ancho de campo distinto del último elemento está establecido en cero o menos. Un ancho de campo menor o igual que cero se puede usar como último elemento para indicar que el último campo es de longitud variable, pero no se puede usar como cualquier otro elemento.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Establezca el ancho de campo en la longitud correcta.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [Procedimiento para leer archivos de texto de ancho fijo](../developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
