---
title: Procedimientos de función (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad4f55a9dd9fbd68c36dd53a01f97ddb03c2bb9b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="function-procedures-visual-basic"></a>Procedimientos de función (Visual Basic)
A `Function` procedimiento es una serie de instrucciones de Visual Basic delimitadas por la `Function` y `End Function` las instrucciones. El `Function` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada. Cuando devuelve el control, también devuelve un valor para el código de llamada.  
  
 Cada vez que se llama al procedimiento, sus instrucciones que se ejecuta, a partir de la primera instrucción ejecutable tras la `Function` instrucción y terminando con la primera `End Function`, `Exit Function`, o `Return` encontrada una instrucción.  
  
 Puede definir un `Function` procedimiento en un módulo, clase o estructura. Es `Public` de forma predeterminada, lo que significa que se puede llamar desde cualquier lugar en la aplicación que tiene acceso el módulo, clase o estructura en el que se ha definido.  
  
 A `Function` procedimiento puede aceptar argumentos, como constantes, variables o expresiones, que se pasan a él por el código de llamada.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 La sintaxis para declarar un `Function` procedimiento es el siguiente:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 El *modificadores* puede especificar un nivel de acceso e información relacionada con la sobrecarga, invalidación, uso compartido y sombreado. Para obtener más información, consulte [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Declarar cada parámetro de la misma manera que lo hace para [Sub (procedimientos)](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo de datos  
 Cada `Function` procedimiento tiene un tipo de datos, solo las variables. Este tipo de datos especificado por la `As` cláusula en la `Function` statement y determina el tipo de datos del valor de la función devuelve al código de llamada. Las siguientes declaraciones de ejemplo muestra cómo hacerlo.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Para obtener más información, vea "Partes" en [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
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
  
-   Asigna un valor a su propio nombre de función en una o más instrucciones del procedimiento. No devolver el control al programa que realiza la llamada hasta que un `Exit Function` o `End Function` se ejecuta la instrucción. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 La ventaja de asignar el valor devuelto al nombre de función es que control no se devuelve desde el procedimiento hasta que encuentra un `Exit Function` o `End Function` instrucción. Esto le permite asignar un valor previo y ajuste más adelante si es necesario.  
  
 Para obtener más información sobre cómo devolver valores, vea [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md). Para obtener información sobre cómo devolver matrices, vea [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Se invoca un `Function` procedimiento mediante la inclusión de su nombre y argumentos en el lado derecho de una instrucción de asignación o en una expresión. Debe proporcionar valores para todos los argumentos que no son opcionales, y debe incluir la lista de argumentos entre paréntesis. Si no se proporcionan argumentos, se pueden omitir los paréntesis.  
  
 La sintaxis de una llamada a un `Function` procedimiento es el siguiente:  
  
 *valor l*`=`*functionname* `[(` *argumentlist*  `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=` *expresión*  `) Then`  
  
 Cuando se llama a un `Function` procedimiento, no es necesario utilizar su valor devuelto. Si no lo hace, se llevan a cabo todas las acciones de la función, pero se omite el valor devuelto. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> se suele denominar de esta manera.  
  
### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaración y llamada  
 El siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los otros dos lados.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)  
 [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
