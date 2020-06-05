---
title: Procedimiento para pasar argumentos a un procedimiento
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
ms.openlocfilehash: 903e05facccd1f2afdf4bb51b200531feb64aa79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387782"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Cómo: Pasar argumentos a un procedimiento (Visual Basic)
Cuando se llama a un procedimiento, se sigue el nombre del procedimiento con una lista de argumentos entre paréntesis. Proporcione un argumento correspondiente a cada parámetro necesario que el procedimiento define y, opcionalmente, puede proporcionar argumentos a los `Optional` parámetros. Si no proporciona un `Optional` parámetro en la llamada, debe incluir una coma para marcar su lugar en la lista de argumentos si está proporcionando los argumentos subsiguientes.  
  
 Si piensa pasar un argumento de un tipo de datos distinto del parámetro correspondiente, como `Byte` a `String` , puede establecer el modificador de comprobación de tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) en `Off` . Si `Option Strict` es `On` , se deben usar conversiones de ampliación o palabras clave de conversión explícita. Para obtener más información, vea [conversiones de ampliación y de restricción](../data-types/widening-and-narrowing-conversions.md) y [funciones de conversión de tipos](../../../language-reference/functions/type-conversion-functions.md).  
  
 Para obtener más información, vea [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Para pasar uno o más argumentos a un procedimiento  
  
1. En la instrucción de llamada, siga el nombre del procedimiento entre paréntesis.  
  
2. Dentro de los paréntesis, coloque una lista de argumentos. Incluya un argumento para cada parámetro necesario que defina el procedimiento y sepárelos con comas.  
  
3. Asegúrese de que cada argumento es una expresión válida que se evalúa como un tipo de datos que se pueda convertir al tipo definido por el procedimiento para el parámetro correspondiente.  
  
4. Si un parámetro se define como [opcional](../../../language-reference/modifiers/optional.md), puede incluirlo en la lista de argumentos u omitirlo. Si lo omite, el procedimiento utiliza el valor predeterminado definido para ese parámetro.  
  
5. Si omite un argumento para un `Optional` parámetro y hay otro parámetro detrás de él en la lista de parámetros, puede marcar el lugar del argumento omitido mediante una coma adicional en la lista de argumentos.  
  
     En el ejemplo siguiente se llama a la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> función Visual Basic.  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     En el ejemplo anterior se proporciona el primer argumento necesario, que es la cadena de mensaje que se va a mostrar. Omite un argumento para el segundo parámetro opcional, que especifica los botones que se van a mostrar en el cuadro de mensaje. Dado que la llamada no proporciona un valor, `MsgBox` usa el valor predeterminado, `MsgBoxStyle.OKOnly` , que solo muestra un botón **Aceptar** .  
  
     La segunda coma de la lista de argumentos marca el lugar del segundo argumento omitido, y la última cadena se pasa al tercer parámetro opcional de `MsgBox` , que es el texto que se va a mostrar en la barra de título.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos Sub](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Procedimientos de operador](./operator-procedures.md)
- [Procedimiento para definir un parámetro para un procedimiento](./how-to-define-a-parameter-for-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Procedimientos recursivos](./recursive-procedures.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Objetos y clases](../objects-and-classes/index.md)
- [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)
