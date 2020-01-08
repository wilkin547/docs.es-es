---
title: 'Cómo: Crear una expresión lambda'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 1c65841e4c124252cfa41bcd4d0c305a426687ee
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75632355"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Cómo: Crear una expresión lambda (Visual Basic)
Una *expresión lambda* es una función o subrutina que no tiene un nombre. Se puede usar una expresión lambda siempre que un tipo de delegado sea válido.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Para crear una función de expresión lambda de una sola línea  
  
1. En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:  
  
     `Dim add1 =`   `Function`  
  
2. Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función. Tenga en cuenta que no especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. Después de la lista de parámetros, escriba una sola expresión como cuerpo de la función. El valor que la expresión evalúa como es el valor devuelto por la función. No use una cláusula `As` para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     Llame a la expresión lambda pasando un argumento entero.  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. Como alternativa, el mismo resultado se logra mediante el ejemplo siguiente:  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Para crear una subrutina de expresión lambda de una sola línea  
  
1. En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Sub`  
  
2. Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina. Tenga en cuenta que no especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     La expresión lambda se llama pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Para crear una función de expresión lambda de varias líneas  
  
1. En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Function`, como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Function`  
  
2. Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función. Tenga en cuenta que no especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. Presione ENTRAR. La instrucción `End Function` se agrega automáticamente.  
  
4. En el cuerpo de la función, agregue el código siguiente para crear una expresión y devolver el valor. No use una cláusula `As` para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     Llame a la expresión lambda pasando un argumento entero.  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Para crear una subrutina de expresión lambda de varias líneas  
  
1. En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente:  
  
     `Dim add1 =`   `Sub`  
  
2. Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina. Tenga en cuenta que no especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. Presione ENTRAR. La instrucción `End Sub` se agrega automáticamente.  
  
4. En el cuerpo de la función, agregue el código siguiente para ejecutarlo cuando se invoque la subrutina.  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     La expresión lambda se llama pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>Ejemplo  
 Un uso común de las expresiones lambda es definir una función que se puede pasar como argumento para un parámetro cuyo tipo es `Delegate`. En el ejemplo siguiente, el método <xref:System.Diagnostics.Process.GetProcesses%2A> devuelve una matriz de los procesos que se ejecutan en el equipo local. El método <xref:System.Linq.Enumerable.Where%2A> de la clase <xref:System.Linq.Enumerable> requiere un delegado `Boolean` como argumento. La expresión lambda en el ejemplo se usa para ese propósito. Devuelve `True` para cada proceso que solo tiene un subproceso y que se seleccionan en `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 El ejemplo anterior es equivalente al código siguiente, que está escrito en la sintaxis Language-Integrated Query (LINQ):  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq.Enumerable>
- [Expresiones lambda](./lambda-expressions.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Paso de procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
