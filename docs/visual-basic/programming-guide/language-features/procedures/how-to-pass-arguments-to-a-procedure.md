---
title: Filtrar Pasar argumentos a un procedimiento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: 0bc7c9d09922b7fbef534e6b58389ca343cc1e13
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974398"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Filtrar Pasar argumentos a un procedimiento (Visual Basic)
Cuando se llama a un procedimiento, siga el nombre del procedimiento con una lista de argumentos entre paréntesis. Se proporciona un argumento correspondiente a cada parámetro necesario que se define el procedimiento y, opcionalmente, puede proporcionar argumentos a la `Optional` parámetros. Si no se suministra un `Optional` parámetro de la llamada, debe incluir una coma para marcar su lugar en la lista de argumentos si está proporcionando los argumentos subsiguientes.  
  
 Si va a pasar un argumento de tipo de datos diferente del parámetro correspondiente, como `Byte` a `String`, puede establecer el modificador de comprobación de tipos ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) a `Off`. Si `Option Strict` es `On`, se deben usar conversiones de ampliación o palabras clave de conversión explícita. Para obtener más información, consulte [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Para obtener más información, consulte [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Para pasar uno o más argumentos a un procedimiento  
  
1.  En la instrucción de llamada, siga el nombre del procedimiento con paréntesis.  
  
2.  Dentro de los paréntesis, coloque una lista de argumentos. Incluir un argumento para cada parámetro necesario que el procedimiento define y separe los argumentos con comas.  
  
3.  Asegúrese de que cada argumento es una expresión válida que se evalúa como un tipo de datos convertible al tipo el procedimiento se define para el parámetro correspondiente.  
  
4.  Si se define un parámetro como [opcional](../../../../visual-basic/language-reference/modifiers/optional.md), puede incluirlo en la lista de argumentos u omitirlo. Si se omite, el procedimiento utiliza el valor predeterminado definido para ese parámetro.  
  
5.  Si se omite un argumento para un `Optional` parámetro y hay otro parámetro después de él en la lista de parámetros, puede marcar el lugar del argumento omitido por una coma adicional en la lista de argumentos.  
  
     El ejemplo siguiente se llama a la de Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> función.  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     El ejemplo anterior proporciona el primer argumento necesario, que es la cadena de mensaje que se mostrará. Omite un argumento para el segundo parámetro opcional que especifica los botones que deben mostrarse en el cuadro de mensaje. Dado que la llamada no proporciona un valor, `MsgBox` utiliza el valor predeterminado, `MsgBoxStyle.OKOnly`, que muestra sólo un **Aceptar** botón.  
  
     El segundo punto y coma en la lista de argumentos marca el lugar del segundo argumento se omite y la última cadena se pasa al tercer parámetro opcional de `MsgBox`, que es el texto que se mostrará en la barra de título.  
  
## <a name="see-also"></a>Vea también

- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Cómo: Definir un parámetro para un procedimiento](./how-to-define-a-parameter-for-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Procedimientos recursivos](./recursive-procedures.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)
