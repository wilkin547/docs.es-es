---
title: "Cómo: Crear una expresión lambda (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16365b64e5430be61c113ac7601154df260e4ca5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Cómo: Crear una expresión lambda (Visual Basic)
A *expresión lambda* es una función o subrutina que no tiene un nombre. Una expresión lambda puede usarse siempre que un tipo de delegado es válido.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Para crear una función de expresión lambda de línea  
  
1.  En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:  
  
     `Dim add1 =`   `Function`  
  
2.  Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función. Tenga en cuenta que no se especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Después de la lista de parámetros, escriba una expresión única como el cuerpo de la función. El valor que la expresión se evalúa como es el valor devuelto por la función. No use un `As` cláusula para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de tipo entero.  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  Como alternativa, se consigue el mismo resultado en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Para crear una subrutina de expresión lambda de línea  
  
1.  En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, tal y como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Sub`  
  
2.  Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina. Tenga en cuenta que no se especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Después de la lista de parámetros, escriba una sola instrucción como el cuerpo de la subrutina.  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Para crear una función de expresión lambda de varias líneas  
  
1.  En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, tal y como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Function`  
  
2.  Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función. Tenga en cuenta que no se especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Presione ENTRAR. El `End Function` instrucción se agrega automáticamente.  
  
4.  Dentro del cuerpo de la función, agregue el código siguiente para crear una expresión y el valor devuelto. No use un `As` cláusula para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de tipo entero.  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Para crear una subrutina de expresión lambda de varias líneas  
  
1.  En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, tal y como se muestra en el ejemplo siguiente:  
  
     `Dim add1 =`   `Sub`  
  
2.  Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina. Tenga en cuenta que no se especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Presione ENTRAR. El `End Sub` instrucción se agrega automáticamente.  
  
4.  Dentro del cuerpo de la función, agregue el código siguiente para ejecutar cuando se invoca la subrutina.  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>Ejemplo  
 Es un uso común de las expresiones lambda definir una función que puede pasarse como argumento para un parámetro cuyo tipo es en `Delegate`. En el ejemplo siguiente, la <xref:System.Diagnostics.Process.GetProcesses%2A> método devuelve una matriz de los procesos que se ejecutan en el equipo local. El <xref:System.Linq.Enumerable.Where%2A> método desde el <xref:System.Linq.Enumerable> clase requiere un `Boolean` delegar como su argumento. La expresión lambda en el ejemplo se usa para ese fin. Devuelve `True` para cada proceso que tiene un solo subproceso y los que están seleccionados en `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 El ejemplo anterior es equivalente al código siguiente, que está escrito en [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] sintaxis:  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.Enumerable>  
 [Expresiones lambda](./lambda-expressions.md)  
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Paso de procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
