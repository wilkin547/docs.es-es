---
title: 'Cómo: Pasar argumentos a un procedimiento (Visual Basic)'
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
ms.openlocfilehash: f393f17f87c5920fb9bfa2a2097c09d48bebdc16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650597"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Cómo: Pasar argumentos a un procedimiento (Visual Basic)
Cuando se llama a un procedimiento, siga el nombre del procedimiento con una lista de argumentos entre paréntesis. Se proporciona un argumento correspondiente a cada parámetro necesario que se define el procedimiento y, opcionalmente, puede proporcionar argumentos a la `Optional` parámetros. Si no se proporciona un `Optional` parámetro en la llamada, debe incluir una coma para marcar su lugar en la lista de argumentos si está proporcionando los argumentos subsiguientes.  
  
 Si desea pasar un argumento de un tipo de datos diferente del parámetro correspondiente, como `Byte` a `String`, puede establecer el modificador de comprobación de tipos ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) a `Off`. Si `Option Strict` es `On`, se debe utilizar conversiones de ampliación o palabras clave de conversión explícita. Para obtener más información, consulte [conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [funciones de conversión de tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Para obtener más información, consulte [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Para pasar uno o más argumentos a un procedimiento  
  
1.  En la instrucción de llamada, siga el nombre del procedimiento con paréntesis.  
  
2.  Dentro de los paréntesis, coloque una lista de argumentos. Incluyen un argumento para cada parámetro necesario que el procedimiento define y separe los argumentos con comas.  
  
3.  Asegúrese de que cada argumento es una expresión válida que se evalúa como un tipo de datos convertible al tipo que el procedimiento se define para el parámetro correspondiente.  
  
4.  Si un parámetro se define como [opcional](../../../../visual-basic/language-reference/modifiers/optional.md), puede incluir en la lista de argumentos u omitirlo. Si se omite, el procedimiento utiliza el valor predeterminado definido para ese parámetro.  
  
5.  Si se omite un argumento para un `Optional` parámetro y hay otro parámetro después de él en la lista de parámetros, puede marcar el lugar del argumento omitido mediante una coma adicional en la lista de argumentos.  
  
     En el ejemplo siguiente se llama Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> función.  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     En el ejemplo anterior se proporciona el primer argumento necesario, que es la cadena de mensaje que se mostrará. Omite un argumento para el segundo parámetro opcional, que especifica los botones que se muestran en el cuadro de mensaje. Dado que la llamada no proporciona un valor, `MsgBox` utiliza el valor predeterminado, `MsgBoxStyle.OKOnly`, que muestra únicamente una **Aceptar** botón.  
  
     El segundo punto y coma en la lista de argumentos marca el lugar del segundo argumento se omite y la última cadena se pasa al tercer parámetro opcional de `MsgBox`, que es el texto que se mostrará en la barra de título.  
  
## <a name="see-also"></a>Vea también

 [Subprocedimientos](./sub-procedures.md)  
 [Procedimientos de función](./function-procedures.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Definir un parámetro para un procedimiento](./how-to-define-a-parameter-for-a-procedure.md)  
 [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)  
 [Procedimientos recursivos](./recursive-procedures.md)  
 [Sobrecarga de procedimientos](./procedure-overloading.md)  
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)  
