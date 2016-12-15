---
title: "C&#243;mo: Crear una expresi&#243;n lambda (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "expresiones [Visual Basic], lambda"
  - "lambda (expresiones) [Visual Basic]"
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Crear una expresi&#243;n lambda (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una *expresión lambda* es una función o subrutina que no tiene un nombre.  Se puede utilizar dondequiera que un tipo delegado sea válido.  
  
### Para crear una función de expresión lambda de una sola línea  
  
1.  En cualquier situación en la que se pueda usar un tipo delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:  
  
     `Dim add1 =`   `Function`  
  
2.  Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función.  Observe que no se especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Después de la lista de parámetros, escriba una sola expresión como cuerpo de la función.  El valor de la expresión es el valor devuelto por la función.  No se usa una cláusula `As` para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de tipo entero.  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  También se obtiene el mismo resultado con el siguiente ejemplo:  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### Para crear una subrutina de expresión lambda de una sola línea  
  
1.  En cualquier situación en la que se pueda usar un tipo delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Sub`  
  
2.  Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina.  Observe que no se especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### Para crear una función de expresión lambda de varias líneas  
  
1.  En cualquier situación en la que se pueda usar un tipo delegado, escriba la palabra clave `Function`, como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Function`  
  
2.  Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función.  Observe que no se especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Presione ENTRAR.  La instrucción `End Function` se agregará automáticamente.  
  
4.  En el cuerpo de la función, agregue el código siguiente para crear una expresión y devolver el valor.  No se usa una cláusula `As` para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de tipo entero.  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### Para crear una subrutina de expresión lambda de varias líneas  
  
1.  En cualquier situación en la que se pueda usar un tipo delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente:  
  
     `Dim add1 =`   `Sub`  
  
2.  Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina.  Observe que no se especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Presione ENTRAR.  La instrucción `End Sub` se agregará automáticamente.  
  
4.  En el cuerpo de la función, agregue el código siguiente para su ejecución cuando se llama a la subrutina.  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Se llama a la expresión lambda pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## Ejemplo  
 Las expresiones lambda se suelen usar para definir una función que se puede pasar como argumento de un parámetro cuyo tipo es `Delegate`.  En el ejemplo siguiente, el método <xref:System.Diagnostics.Process.GetProcesses%2A> devuelve una matriz de los procesos que se ejecutan en el equipo local.  El método <xref:System.Linq.Enumerable.Where%2A> de la clase <xref:System.Linq.Enumerable> requiere un delegado de tipo `Boolean` como argumento.  La expresión lambda del ejemplo se utiliza con ese fin.  Devuelve `True` para cada uno de los procesos que tienen solamente un subproceso, los cuales están seleccionados en `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 El ejemplo anterior es equivalente al código siguiente, escrito con la sintaxis de [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]:  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## Vea también  
 <xref:System.Linq.Enumerable>   
 [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Delegate \(Instrucción\)](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)