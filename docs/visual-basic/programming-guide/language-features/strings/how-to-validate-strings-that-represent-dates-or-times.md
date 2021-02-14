---
description: 'Más información acerca de cómo: validar cadenas que representan fechas u horas (Visual Basic)'
title: Procedimiento para validar cadenas que representan fechas u horas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 4e9255717d1711d8e9839c218a78b359549d9eef
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424260"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Cómo: Validar cadenas que representan fechas u horas (Visual Basic)

En el ejemplo de código siguiente se establece un `Boolean` valor que indica si una cadena representa una fecha u hora válida.  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>Compilar el código  

 Reemplace `("01/01/03")` y `"9:30 PM"` por la fecha y hora que desea validar. Puede reemplazar la cadena por otra cadena codificada de forma rígida, por una `String` variable, o por un método que devuelva una cadena, como `InputBox` .  
  
## <a name="robust-programming"></a>Programación sólida  

 Utilice este método para validar la cadena antes de intentar convertir `String` en una `DateTime` variable. Al comprobar la fecha o la hora en primer lugar, puede evitar generar una excepción en tiempo de ejecución.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Validar cadenas en Visual Basic](validating-strings.md)
