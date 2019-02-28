---
title: Filtrar Validar cadenas que representan fechas u horas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: c1a3f14354e36dec91aca3afbe8470eff7146318
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970415"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Procedimiento Validar cadenas que representan fechas u horas (Visual Basic)
El siguiente ejemplo de código establece un `Boolean` valor que indica si una cadena representa una fecha u hora válida.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Reemplace `("01/01/03")` y `"9:30 PM"` con la fecha y hora que desea validar. Puede reemplazar la cadena con otra cadena codificada de forma rígida, con un `String` o variable, con un método que devuelve una cadena, como `InputBox`.  
  
## <a name="robust-programming"></a>Programación sólida  
 Use este método para validar la cadena antes de intentar convertir el `String` a un `DateTime` variable. Comprobando la fecha u hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
