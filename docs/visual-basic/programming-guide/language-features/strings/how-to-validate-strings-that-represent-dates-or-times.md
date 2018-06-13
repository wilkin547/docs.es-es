---
title: 'Cómo: Validar cadenas que representan fechas u horas (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 411c8517783421b2472c3e4aa77287f8252f179b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647867"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Cómo: Validar cadenas que representan fechas u horas (Visual Basic)
El siguiente ejemplo de código establece una `Boolean` valor que indica si una cadena representa una fecha u hora válida.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Reemplace `("01/01/03")` y `"9:30 PM"` con la fecha y hora que desea validar. Puede reemplazar la cadena con otra cadena codificada de forma rígida, con un `String` o variable, con un método que devuelve una cadena, como `InputBox`.  
  
## <a name="robust-programming"></a>Programación sólida  
 Utilice este método para validar la cadena antes de intentar convertir el `String` a una `DateTime` variable. Comprobando la fecha u hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
