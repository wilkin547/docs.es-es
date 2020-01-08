---
title: 'Cómo: Validar cadenas que representan fechas u horas'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5321e7a85c45ddb6ce17433bd25ce9ca2165f0a3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348412"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Cómo: Validar cadenas que representan fechas u horas (Visual Basic)
En el ejemplo de código siguiente se establece un valor de `Boolean` que indica si una cadena representa una fecha u hora válida.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>Compilar el código  
 Reemplace `("01/01/03")` y `"9:30 PM"` por la fecha y la hora que desea validar. Puede reemplazar la cadena por otra cadena codificada de forma rígida, por una `String` variable, o por un método que devuelva una cadena, como `InputBox`.  
  
## <a name="robust-programming"></a>Programación sólida  
 Utilice este método para validar la cadena antes de intentar convertir el `String` en una variable de `DateTime`. Al comprobar la fecha o la hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
