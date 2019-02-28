---
title: Procedimientos de función (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: f1e2c707b3caa8c7cc49a6f33840ebdfd0c89f4e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968652"
---
# <a name="function-procedures-visual-basic"></a>Procedimientos de función (Visual Basic)
Un `Function` procedimiento es una serie de instrucciones de Visual Basic está incluido en el `Function` y `End Function` instrucciones. El `Function` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada. Cuando devuelve el control, también devuelve un valor al código de llamada.  
  
 Cada vez que se llama al procedimiento, se ejecutan, las instrucciones a partir de la primera instrucción ejecutable tras el `Function` instrucción y terminando por la primera `End Function`, `Exit Function`, o `Return` encontrada una instrucción.  
  
 Puede definir un `Function` procedimiento en un módulo, clase o estructura. Es `Public` de forma predeterminada, lo que significa que se puede llamar desde cualquier lugar en la aplicación que tiene acceso al módulo, clase o estructura en el que se define.  
  
 Un `Function` procedimiento puede tomar argumentos, como constantes, variables o expresiones, que se pasan a él por el código de llamada.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 La sintaxis para declarar un `Function` es el procedimiento siguiente:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 El *modificadores* puede especificar el nivel de acceso e información sobre la sobrecarga, invalidación, uso compartido y sombreado. Para obtener más información, consulte [instrucción Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Declarar cada parámetro de la misma manera que lo hace para [subprocedimientos](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo de datos  
 Cada `Function` procedimiento tiene un tipo de datos, solo las variables. Este tipo de datos especificado por el `As` cláusula en la `Function` statement y determina el tipo de datos del valor que devuelve la función al código de llamada. Las siguientes declaraciones de ejemplo muestra cómo hacerlo.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Para obtener más información, vea "Elementos" en [instrucción Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Devolver valores  
 El valor de un `Function` procedimiento envía de vuelta al código de llamada se llama a su valor devuelto. El procedimiento devuelve este valor en uno de dos maneras:  
  
-   Usa el `Return` instrucción para especificar el valor devuelto y devuelve el control inmediatamente al programa que realiza la llamada. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   Asigna un valor a su propio nombre de función en una o varias instrucciones del procedimiento. No devolver el control al programa que realiza la llamada hasta que un `Exit Function` o `End Function` se ejecuta la instrucción. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 La ventaja de asignar el valor devuelto para el nombre de función es ese control no se devuelve desde el procedimiento hasta que encuentra un `Exit Function` o `End Function` instrucción. Esto permite asignar un valor previo y posterior ajuste si es necesario.  
  
 Para obtener más información sobre cómo devolver valores, vea [instrucción Function](../../../../visual-basic/language-reference/statements/function-statement.md). Para obtener información sobre cómo devolver matrices, vea [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Se invoca un `Function` procedimiento mediante la inclusión de su nombre y argumentos en el lado derecho de una instrucción de asignación o en una expresión. Debe proporcionar valores para todos los argumentos que no son opcionales, y debe incluir la lista de argumentos entre paréntesis. Si se proporciona ningún argumento, opcionalmente, puede omitir los paréntesis.  
  
 La sintaxis para llamar a un `Function` es el procedimiento siguiente:  
  
 *valor l*`=`*functionname* `[(` *argumentlist* `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=` *expresión* `) Then`  
  
 Cuando se llama a un `Function` procedimiento, no es necesario usar el valor devuelto. Si no lo hace, se realizan todas las acciones de la función, pero se omite el valor devuelto. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> a menudo se denomina de esta manera.  
  
### <a name="illustration-of-declaration-and-call"></a>Ilustración de la declaración y llamada  
 La siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los dos lados.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 El ejemplo siguiente muestra una llamada típica al `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también
- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Cómo: Crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)
- [Cómo: Devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)
- [Cómo: Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
