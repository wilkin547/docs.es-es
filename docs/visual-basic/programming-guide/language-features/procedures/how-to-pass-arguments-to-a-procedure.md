---
title: 'Cómo: Pasar argumentos a un procedimiento'
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
ms.openlocfilehash: 0267eed7c145988d61de715fd661bd4906d8d57d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344841"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Cómo: Pasar argumentos a un procedimiento (Visual Basic)
Cuando se llama a un procedimiento, se sigue el nombre del procedimiento con una lista de argumentos entre paréntesis. Proporcione un argumento correspondiente a cada parámetro necesario que el procedimiento define y, opcionalmente, puede proporcionar argumentos a los parámetros de `Optional`. Si no proporciona un parámetro `Optional` en la llamada, debe incluir una coma para marcar su lugar en la lista de argumentos si está proporcionando los argumentos subsiguientes.  
  
 Si piensa pasar un argumento de un tipo de datos distinto del parámetro correspondiente, como `Byte` a `String`, puede establecer el modificador de comprobación de tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) en `Off`. Si `Option Strict` es `On`, debe utilizar las conversiones de ampliación o las palabras clave de conversión explícita. Para obtener más información, vea [conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Para obtener más información, vea [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Para pasar uno o más argumentos a un procedimiento  
  
1. En la instrucción de llamada, siga el nombre del procedimiento entre paréntesis.  
  
2. Dentro de los paréntesis, coloque una lista de argumentos. Incluya un argumento para cada parámetro necesario que defina el procedimiento y sepárelos con comas.  
  
3. Asegúrese de que cada argumento es una expresión válida que se evalúa como un tipo de datos que se pueda convertir al tipo definido por el procedimiento para el parámetro correspondiente.  
  
4. Si un parámetro se define como [opcional](../../../../visual-basic/language-reference/modifiers/optional.md), puede incluirlo en la lista de argumentos u omitirlo. Si lo omite, el procedimiento utiliza el valor predeterminado definido para ese parámetro.  
  
5. Si omite un argumento para un parámetro de `Optional` y hay otro parámetro después de él en la lista de parámetros, puede marcar el lugar del argumento omitido mediante una coma adicional en la lista de argumentos.  
  
     En el ejemplo siguiente se llama a la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> de Visual Basic.  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     En el ejemplo anterior se proporciona el primer argumento necesario, que es la cadena de mensaje que se va a mostrar. Omite un argumento para el segundo parámetro opcional, que especifica los botones que se van a mostrar en el cuadro de mensaje. Dado que la llamada no proporciona un valor, `MsgBox` usa el valor predeterminado, `MsgBoxStyle.OKOnly`, que muestra solo un botón **Aceptar** .  
  
     La segunda coma de la lista de argumentos marca el lugar del segundo argumento omitido, y la última cadena se pasa al tercer parámetro opcional de `MsgBox`, que es el texto que se va a mostrar en la barra de título.  
  
## <a name="see-also"></a>Vea también

- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Definir un parámetro para un procedimiento](./how-to-define-a-parameter-for-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Procedimientos recursivos](./recursive-procedures.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)
