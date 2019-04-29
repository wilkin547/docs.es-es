---
title: Procedimiento Crear una expresión Lambda (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665941"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Procedimiento Crear una expresión Lambda (Visual Basic)
Un *expresión lambda* es una función o subrutina que no tiene un nombre. Una expresión lambda puede usarse siempre que sea un tipo de delegado es válido.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Para crear una función de la expresión lambda de línea  
  
1. En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:  
  
     `Dim add1 =`   `Function`  
  
2. Entre paréntesis, directamente después `Function`, escriba los parámetros de la función. Tenga en cuenta que no se especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. Después de la lista de parámetros, escriba una expresión única como el cuerpo de la función. El valor que se evalúa como la expresión es el valor devuelto por la función. No se usa un `As` cláusula para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     Se llama a la expresión lambda pasando un argumento entero.  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. Como alternativa, se consigue el mismo resultado en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Para crear una subrutina de expresión lambda de línea  
  
1. En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Sub`  
  
2. Entre paréntesis, directamente después `Sub`, escriba los parámetros de la subrutina. Tenga en cuenta que no se especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     Se llama a la expresión lambda pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Para crear una función de la expresión lambda de varias líneas  
  
1. En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como se muestra en el ejemplo siguiente.  
  
     `Dim add1 =`   `Function`  
  
2. Entre paréntesis, directamente después `Function`, escriba los parámetros de la función. Tenga en cuenta que no se especifica un nombre después de `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. Presione ENTRAR. El `End Function` instrucción se agrega automáticamente.  
  
4. Dentro del cuerpo de la función, agregue el código siguiente para crear una expresión y el valor devuelto. No se usa un `As` cláusula para especificar el tipo de valor devuelto.  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     Se llama a la expresión lambda pasando un argumento entero.  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Para crear una subrutina de expresión lambda de varias líneas  
  
1. En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente:  
  
     `Dim add1 =`   `Sub`  
  
2. Entre paréntesis, directamente después `Sub`, escriba los parámetros de la subrutina. Tenga en cuenta que no se especifica un nombre después de `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. Presione ENTRAR. El `End Sub` instrucción se agrega automáticamente.  
  
4. Dentro del cuerpo de la función, agregue el código siguiente para ejecutar cuando se invoca la subrutina.  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     Se llama a la expresión lambda pasando un argumento de cadena.  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>Ejemplo  
 Es un uso común de las expresiones lambda definir una función que puede pasarse como argumento para un parámetro cuyo tipo es `Delegate`. En el ejemplo siguiente, la <xref:System.Diagnostics.Process.GetProcesses%2A> método devuelve una matriz de los procesos que se ejecutan en el equipo local. El <xref:System.Linq.Enumerable.Where%2A> método desde el <xref:System.Linq.Enumerable> clase requiere un `Boolean` delegar como su argumento. La expresión lambda en el ejemplo se usa para ese propósito. Devuelve `True` para cada proceso que tiene un solo subproceso, y que estén seleccionadas en `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 El ejemplo anterior es equivalente al código siguiente, que está escrito en [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] sintaxis:  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq.Enumerable>
- [Expresiones lambda](./lambda-expressions.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
