---
title: Function (procedimientos) (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Function procedures
- return values, function procedures
- Visual Basic code, procedures
- procedures, calling
- procedures, Function procedures
- syntax, function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 11baaa6985f0681aa9c67c4f2470fb9917db5b78
ms.lasthandoff: 03/13/2017

---
# <a name="function-procedures-visual-basic"></a>Procedimientos de función (Visual Basic)
Un `Function` procedimiento es una serie de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] instrucciones delimitadas por la `Function` y `End Function` instrucciones. El `Function` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada. Cuando devuelve el control, también devuelve un valor al código de llamada.  
  
 Cada vez que se llama al procedimiento, se ejecutan, las instrucciones a partir de la primera instrucción ejecutable tras la `Function` instrucción y terminando por la primera `End Function`, `Exit Function`, o `Return` instrucción que se encuentre.  
  
 Puede definir un `Function` procedimiento en un módulo, clase o estructura. Es `Public` de forma predeterminada, lo que significa que se puede llamar desde cualquier lugar en la aplicación que tiene acceso el módulo, clase o estructura en el que se ha definido.  
  
 Un `Function` procedimiento puede tomar argumentos, como constantes, variables o expresiones, que le pasa el código de llamada.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 La sintaxis para declarar un `Function` procedimiento es el siguiente:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 El *modificadores* puede especificar un nivel de acceso e información relacionada con la sobrecarga, invalidación, uso compartido y sombreado. Para obtener más información, consulte [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Declara cada parámetro de la misma manera que lo hace para [procedimientos Sub](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo de datos  
 Cada `Function` procedimiento tiene un tipo de datos, solo las variables. Este tipo de datos especificado por la `As` cláusula en la `Function` statement y determina el tipo de datos del valor de la función devuelve al código de llamada. Las siguientes declaraciones de ejemplo se muestra cómo hacerlo.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Para obtener más información, vea "Partes" en [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Devolver valores  
 El valor de un `Function` procedimiento envía de nuevo en el código de llamada se llama a su valor devuelto. El procedimiento devuelve este valor en uno de dos maneras:  
  
-   Utiliza el `Return` para especificar el valor devuelto y devuelve el control inmediatamente al programa de llamada. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   Asigna un valor a su propio nombre de función en una o más instrucciones del procedimiento. No devolver el control al programa de llamada hasta que un `Exit Function` o `End Function` se ejecuta la instrucción. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 La ventaja de asignar el valor devuelto al nombre de función es que control en el procedimiento hasta que encuentra un `Exit Function` o `End Function` instrucción. Esto le permite asignar un valor previo y ajustar posteriormente si es necesario.  
  
 Para obtener más información sobre cómo devolver valores, consulte [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md). Para obtener información sobre cómo devolver matrices, vea [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Invocar un `Function` procedimiento incluyendo el nombre y los argumentos en el lado derecho de una instrucción de asignación o en una expresión. Debe proporcionar valores para todos los argumentos que no sean opcionales, y debe incluir la lista de argumentos entre paréntesis. Si no se proporcionan argumentos, se pueden omitir los paréntesis.  
  
 La sintaxis para llamar a un `Function` procedimiento es el siguiente:  
  
 *valor l*`=`*functionname* `[(` *argumentlist*    `)]`  
  
 `If ((`*functionname* `[(` *argumentlist* `)] / 3) <=` *expresión*  `) Then`  
  
 Cuando se llama a un `Function` procedimiento, no es necesario utilizar su valor devuelto. Si no lo hace, se realizan todas las acciones de la función, pero se omite el valor devuelto. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>se suele llamar de esta manera.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
### <a name="illustration-of-declaration-and-call"></a>Ejemplo de declaración y llamada  
 La siguiente `Function` procedimiento calcula el lado más largo o la hipotenusa de un triángulo rectángulo a partir de los valores de los dos lados.  
  
 [!code-vb[1 VbVbcnProcedures](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures Nº&6;](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Sub (procedimientos)](./sub-procedures.md)   
 [Property (procedimientos)](./property-procedures.md)   
 [Procedimientos de operadores](./operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Cómo: crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Cómo: devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)   
 [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
