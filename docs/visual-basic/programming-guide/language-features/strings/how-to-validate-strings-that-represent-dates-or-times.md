---
title: Procedimiento para validar cadenas que representan fechas u horas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: f3654894e274404410179dab04422e20f6040440
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072605"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Cómo: Validar cadenas que representan fechas u horas (Visual Basic)

En el ejemplo de código siguiente se establece un `Boolean` valor que indica si una cadena representa una fecha u hora válida.  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>Compilar el código  

 Reemplace `("01/01/03")` y `"9:30 PM"` por la fecha y hora que desea validar. Puede reemplazar la cadena por otra cadena codificada de forma rígida, por una `String` variable, o por un método que devuelva una cadena, como `InputBox` .  
  
## <a name="robust-programming"></a>Programación sólida  

 Utilice este método para validar la cadena antes de intentar convertir `String` en una `DateTime` variable. Al comprobar la fecha o la hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Validar cadenas en Visual Basic](validating-strings.md)
