---
title: "Cómo: crear una expresión Lambda (Visual Basic) | Documentos de Microsoft"
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
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5e105e87b1e63218f2c3c2204350257c139b5837
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Cómo: Crear una expresión lambda (Visual Basic)
Un *expresión lambda* es una función o subrutina que no tiene un nombre. Una expresión lambda se puede utilizar siempre que sea un tipo de delegado es válido.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Para crear una función de expresión lambda de línea  
  
1.  En cualquier situación donde se podría utilizar un tipo de delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:  
  
     `Dim add1 =`   `Function`  
  
2.  Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función. Observe que no se especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Después de la lista de parámetros, escriba una expresión única como el cuerpo de la función. El valor que la expresión se evalúa como es el valor devuelto por la función. No use un `As` cláusula para especificar el tipo de valor devuelto.  
  
     [!code-vb[1 VbVbalrLambdas](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     Se llama a la expresión lambda pasando un argumento entero.  
  
     [!code-vb[VbVbalrLambdas&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  Como alternativa, se consigue el mismo resultado en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrLambdas&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Para crear una subrutina de expresión lambda de línea  
  
1.  En cualquier situación donde se podría utilizar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Sub`  
  
2.  Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina. Observe que no se especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.  
  
     [!code-vb[VbVbalrLambdas&#17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas&#18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Para crear una función de expresión lambda de varias líneas  
  
1.  En cualquier situación donde se podría utilizar un tipo de delegado, escriba la palabra clave `Function`, como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Function`  
  
2.  Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función. Observe que no se especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Presione ENTRAR. El `End Function` instrucción se agrega automáticamente.  
  
4.  En el cuerpo de la función, agregue el código siguiente para crear una expresión y el valor devuelto. No use un `As` cláusula para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas Nº&19;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     Se llama a la expresión lambda pasando un argumento entero.  
  
     [!code-vb[VbVbalrLambdas&#20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Para crear una subrutina de expresión lambda de varias líneas  
  
1.  En cualquier situación donde se podría utilizar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente:  
  
     `Dim add1 =`   `Sub`  
  
2.  Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina. Observe que no se especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Presione ENTRAR. El `End Sub` instrucción se agrega automáticamente.  
  
4.  En el cuerpo de la función, agregue el siguiente código para ejecutar cuando se invoca la subrutina.  
  
     [!code-vb[21 VbVbalrLambdas](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas&#22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>Ejemplo  
 Un uso común de las expresiones lambda es definir una función que puede pasarse como argumento para un parámetro cuyo tipo sea en `Delegate`. En el ejemplo siguiente, la <xref:System.Diagnostics.Process.GetProcesses%2A>método devuelve una matriz de los procesos en ejecución en el equipo local.</xref:System.Diagnostics.Process.GetProcesses%2A> El <xref:System.Linq.Enumerable.Where%2A>método desde el <xref:System.Linq.Enumerable>clase requiere un `Boolean` delegado como argumento.</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A> La expresión lambda en el ejemplo se usa para ese propósito. Devuelve `True` para cada proceso que tiene un solo subproceso y los que están seleccionados en `filteredList`.  
  
 [!code-vb[VbVbalrLambdas&#10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 El ejemplo anterior es equivalente al código siguiente, que está escrito en [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] sintaxis:  
  
 [!code-vb[VbVbalrLambdas&#11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [Expresiones lambda](./lambda-expressions.md)   
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Cómo: pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
